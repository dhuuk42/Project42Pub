# Project42 — User Guide

Project42 is a private, self-hosted group fitness tracker for weight loss, habits, challenges, and activity tracking. This guide explains everything you need to know to get the most out of it.

> German version: [README_DE.md](README_DE.md)

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Dashboard](#dashboard)
3. [Weight Tracking](#weight-tracking)
4. [Habits](#habits)
5. [Challenges](#challenges)
6. [Activity Feed](#activity-feed)
7. [Scoreboard](#scoreboard)
8. [Recipes](#recipes)
9. [Profile & Settings](#profile--settings)
10. [Home Assistant Integration](#home-assistant-integration)
11. [Withings Integration](#withings-integration)
12. [Share Page](#share-page)

---

## Getting Started

1. You need an **invite code** from the group admin to register (the very first user registers without one and becomes admin automatically).
2. Go to the app URL → **Register** → enter your name, email, password, and invite code.
3. Set up your profile (height, start weight, goal weight) so the scoreboard and BMI calculations work correctly.

---

## Dashboard

Your personal home screen. It shows:

- **Weight check-in** — log today's weight right from the dashboard
- **Current weight & streak** — how many consecutive days you've logged
- **Habits Today** — today's scheduled habits with one-tap check-off
- **Active Challenges** — days remaining in each challenge you've joined
- **Recent Activity** — latest actions from the whole group
- **Leaderboard** — quick view of who's leading
- **Quote of the Day** — daily motivational quote (can be disabled in Profile)

### Customising the dashboard

Tap **Customize** (top right) to toggle widgets on or off and drag them into the order you prefer. Tap **Done** to save.

---

## Weight Tracking

Go to **Weight** in the navigation.

### Logging weight

Fill in:
- **Weight (kg)** — required
- **Date** — defaults to today
- **Body Fat %** — optional
- **Note** — optional (e.g. "after workout")

Tap **Add Entry**.

### Charts & stats

The page shows your weight over time as a chart, plus your current weight, total lost, streak, and number of entries.

### Editing & deleting entries

Each entry in the list has **Edit** and **Delete** buttons. Deleted entries are permanent.

### Import / Export

- **Export My Data** — downloads all your weight entries as a CSV
- **Download Template** — get a blank CSV you can fill in and import
- **Import from CSV** — upload a filled CSV; the app auto-detects date formats (YYYY-MM-DD, DD.MM.YYYY, MM/DD/YYYY, etc.)

---

## Habits

Go to **Habits** in the navigation.

### Creating a habit

Tap **+ Add Habit** and fill in:
- **Name** — e.g. "Drink water", "Morning run"
- **Color** — for the calendar view
- **Frequency** — choose one:
  - *Every day* — appears daily
  - *Specific days* — pick which weekdays
  - *X times/week* — appears every day but only requires N check-offs per week

### Checking off habits

Today's scheduled habits appear under **Today's Habits**. Tap the checkbox to mark one done. Your current streak is shown as a badge.

### Weekly overview

The calendar grid shows the last 7 days — green = completed, grey = missed, empty = not scheduled.

### Managing habits

Under **Manage Habits** you can edit, archive, or delete habits. Archived habits keep their history but no longer appear in Today's view. You can restore them later.

---

## Challenges

Go to **Challenges** in the navigation.

Challenges have two types:

### Check-in challenges (daily)

Each participant taps **Check in for today** once per day. Use this for streaks, consistency goals, or habits done as a group (e.g. "30-Day Plank Challenge").

### Quantity challenges (km, min, reps…)

Each participant logs a numeric value (e.g. 20 km cycling). Multiple entries per day are allowed. The leaderboard ranks by total accumulated value. Use this for distance goals, time-based challenges, or rep counts.

### Creating a challenge

Tap **+ New Challenge** and fill in:
- **Name** — e.g. "100 km Cycling Challenge"
- **Description** — optional goal description
- **Start / End dates**
- **Type** — Check-in or Quantity
- *(Quantity only)* **Goal** and **Unit** — e.g. 100 km

### Joining & leaving

Open a challenge card → tap **Join**. You can leave at any time.

### Logging activity (quantity challenges)

Inside the challenge: enter an **Amount**, optionally a **Date** (defaults to today) and a **Note**, then tap **Log**. Your entries appear in the activity log and your total updates on the leaderboard.

### Leaderboard

Shows all participants ranked by total value (quantity) or check-in count (check-in type).

---

## Activity Feed

Go to **Feed** in the navigation.

Shows a chronological list of everyone's recent activity — weight check-ins, habits completed, new recipes, and challenge check-ins. Use the dropdown to filter by last 3, 7, 14, or 30 days.

---

## Scoreboard

Go to **Scoreboard** in the navigation.

Rankings by **total weight lost** (start weight minus current weight). Also shows BMI, FFMI, streak, and number of entries per user.

Switch between **Everyone** (group view) and **Only Me** (your own history).

---

## Recipes

Go to **Recipes** in the navigation. Share favourite meals with the group — add ingredients, instructions, macros, and photos.

---

## Profile & Settings

Go to **Profile** in the navigation.

### Personal data

- **Name, Email** — basic account info
- **Height, Start weight, Goal weight** — used for BMI, FFMI, and scoreboard calculations
- **Birthdate, Gender** — used for FFMI calculation
- **Telegram Username** — optional; the bot uses this to tag you in group messages

### Appearance

- **Show daily quote** — toggle the motivational quote on the dashboard
- **Banner color** — accent color for your public landing page
- **Bio** — short text shown on your public landing page

### Password reset

If you forget your password, ask the admin to generate a reset token for you in the Admin panel. You'll get a token to use at `/reset-password`.

---

## Home Assistant Integration

Connect the **Home Assistant companion app** (iOS or Android) to push your daily health data — steps, distance, floors, active calories, and heart rate — directly into Project42.

### How it works

1. Your phone or smartwatch syncs health data to the Home Assistant companion app
2. A Home Assistant automation fires twice a day (noon + 22:00 by default)
3. The automation calls Project42's webhook with your latest sensor values
4. Project42 stores the data and shows it on your Profile

### Setup — 4 steps

#### Step 1 — One-time configuration.yaml change

Add the following to your HA `configuration.yaml` **once** (shared by all users on the same HA instance):

```yaml
rest_command:
  http_post:
    url: "{{ url }}"
    method: POST
    content_type: "application/json"
    payload: "{{ payload }}"
```

> **Already have a `rest_command:` block?** Do **not** add a second one — YAML forbids duplicate keys and HA will throw an error. Instead, add only the `http_post:` entry inside your existing block:
>
> ```yaml
> rest_command:
>   my_existing_command:   # whatever was already here
>     ...
>   http_post:             # add only this
>     url: "{{ url }}"
>     method: POST
>     content_type: "application/json"
>     payload: "{{ payload }}"
> ```

Then go to **Developer Tools → Quick Reload → REST Command**.

#### Step 2 — Import the blueprint

In HA: **Settings → Automations → Blueprints → Import Blueprint**

Paste this URL:
```
https://raw.githubusercontent.com/dhuuk42/Project42Pub/main/project42_blueprint.yaml
```

#### Step 3 — Get your webhook URL

1. Open Project42 → **Profile** → **Home Assistant**
2. Click **Generate Webhook Token**
3. Copy the full URL shown — it looks like `https://huukdev.de/api/webhooks/ha/abc123...`

Keep this URL secret — it grants write access to your health data.

#### Step 4 — Create the automation

1. In HA: **Settings → Automations → Create Automation → From Blueprint**
2. Select **Project42 Daily Sync**
3. Fill in:
   - **Webhook URL** — your personal URL from Step 3
   - **Steps Sensor** — search your device name (e.g. `iphone_16pro_yourname`)
   - **Distance Sensor** — optional
   - **Floors Sensor** — optional
   - **Active Calories Sensor** — optional (Apple Watch only)
   - **Heart Rate Sensor** — optional (Apple Watch only)
   - **Sync times** — default is noon + 22:00; adjust as you like
4. Save

Each person creates **their own automation** from the same blueprint with their own webhook URL and sensors.

### Enabling health sensors in the companion app

#### iOS

1. HA Companion App → **Settings** → **Companion App** → **Health**
2. Enable: Steps, Distance (Walking + Running), Flights Climbed
3. Apple Watch users: also enable Active Energy Burned and Heart Rate
4. Grant the permissions iOS asks for

#### Android

1. HA Companion App → **Settings** → **Companion App** → **Manage Sensors**
2. Search "step" → enable **Step counter**
3. Grant Health Connect permissions

### Available sensors by device

| Sensor | iPhone only | iPhone + Apple Watch |
|--------|-------------|----------------------|
| Steps | ✓ | ✓ |
| Distance | ✓ (meters) | ✓ (meters) |
| Floors ascended | ✓ | ✓ |
| Active Calories | — | ✓ |
| Heart Rate | — | ✓ |

> iOS reports distance in **meters** — the blueprint handles this automatically.

### Finding your sensor entity IDs

1. HA → **Developer Tools → States**
2. Filter by your device name (e.g. `iphone_16pro_mirco`)

Common patterns:
```
sensor.{device_name}_steps
sensor.{device_name}_distance
sensor.{device_name}_floors_ascended
sensor.{device_name}_active_energy     ← Apple Watch only
sensor.{device_name}_heart_rate        ← Apple Watch only
```

### Troubleshooting

| Problem | Fix |
|---------|-----|
| Sensors show "unavailable" | Grant health permissions in the companion app; toggle sensors off and on |
| Calories/HR missing | Requires Apple Watch paired and syncing to Apple Health |
| Webhook returns 401 | Token was regenerated — get the new URL from Profile → Home Assistant |
| Steps are 0 | iOS sensors update on a schedule; check the value in Developer Tools → States first |
| Automation trace shows template errors | Make sure you reloaded REST Command after editing configuration.yaml |

---

## Withings Integration

Connect a **Withings scale** (Body+, Body Comp, etc.) to automatically import weight, body fat, blood pressure, heart rate, activity, and sleep data.

1. Profile → **Withings** → **Connect Withings Account**
2. Log in to your Withings account and grant access
3. Tap **Sync Now** to import your data

Imported weight entries appear in your weight history and count toward the scoreboard.

---

## Share Page

Generate a **read-only public link** to share your progress with family or friends — no account needed.

1. Profile → **Family Share Link** → **Generate Share Link**
2. Copy the link and share it
3. The recipient sees your current weight, total lost, streak, and goal progress
4. Tap **Revoke link** to deactivate it at any time

---

*Project42 is self-hosted and private — your data never leaves the group's server.*
