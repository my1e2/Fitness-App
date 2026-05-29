# Train — Fitness App

**A guided workout companion for all fitness levels, from first-timers to seasoned gym-goers.**

---

## Overview

**Train** is a fitness improvement app designed to make structured, personalized workouts accessible to everyone — regardless of experience, body type, or available equipment. Rather than focusing on nutrition and calorie counting like many existing apps (MyFitnessPal, Nutrition Coach, Yuka), Train carves out its own space by centering entirely on **exercise guidance, proper form, and personal progress tracking**.

Users begin by setting up a profile with basic info (name, age, gender), then immediately gain access to a curated workout library they can filter by body region, difficulty, and location (home or gym). Every exercise comes with video tutorials, rep/set recommendations, and muscle group details — so users always know what to do and how to do it safely.

---

## Features

- **Workout Library** — Browse and filter exercises by body area (Core, Upper Body, Lower Body, Back), difficulty (Easy / Medium / Hard), and setting (Home / Gym)
- **Instructional Video Tutorials** — Each exercise is paired with a walkthrough video to reinforce proper form and reduce injury risk
- **Sets & Reps Guidance** — Every workout includes a recommended rep and set scheme tailored to the exercise
- **Muscle Group Targeting** — Filter by specific muscles (Biceps, Glutes, Hamstrings, Deltoids, and 15+ more) to build focused routines
- **Spotter Awareness** — Exercises indicate whether a spotter is recommended
- **Built-in Weight Tracker** — Log weight over time and visualize progress through an interactive line graph
- **Workout Scheduling** — Plan and organize workout routines across daily, weekly, monthly, or yearly timeframes
- **Age-Gated Onboarding** — App is open to users 16+; nutritional tools are restricted to users 18+ to encourage healthy habits in younger users

---

## Target Users

| User Type | Description |
|-----------|-------------|
| **Beginners** | Users new to fitness who need structure, guidance, and beginner-friendly routines to build confidence and avoid injury |
| **Intermediate/Advanced** | Users who know the basics but want variety — easily searchable library removes the "what should I do today?" problem |
| **Home Workout Users** | Exercises filterable to home-compatible workouts, no gym membership required |

> No requirements on weight, height, or fitness level. As long as a user wants to improve, Train is built for them.

---

## Data Model

### Exercise
| Property | Type | Filterable |
|----------|------|------------|
| Exercise Name | String | Yes |
| Body Area | Controlled Vocab (`Core`, `Upper Body`, `Lower Body`, `Back`) | Yes |
| Muscle Group | Controlled Vocab (18 specific muscles) | Yes |
| Difficulty | Controlled Vocab (`Easy`, `Medium`, `Hard`) | Yes |
| Location | Controlled Vocab (`Home`, `Gym`) | Yes |
| Reps & Sets | String | No |
| Video | Embedded MP4 | No |
| Spotter Required | `Yes` / `No` | Yes |

### User Profile
| Property | Type | Required |
|----------|------|----------|
| First & Last Name | String | Yes |
| Username / Password | String | Yes |
| User ID | String (auto-assigned) | Yes |
| Gender | Controlled Vocab | No |
| Profile Picture | JPG (upload) | No |

### Weight Tracker
| Property | Type | Required |
|----------|------|----------|
| Username | String reference | Yes |
| Weight | Integer (lbs) | Yes |
| Date | Date | Yes |
| Weigh-in Baseline | String (starting weight + date) | Yes |

---

## Architecture & Design

- **UI/UX Prototyping:** Designed in [Figma](https://www.figma.com/team_invite/redeem/hxeeCXMPM8JtW2w4jf9kXO)
- **Core Screens:** Home, Search/Filter, Search Results, Exercise Detail, Profile, Weight Tracker, Settings
- **Data Sources:** Self-curated starter library — trend-sourced exercises (dev-reviewed before publishing) — integration with publicly available, consistently updated exercise databases
- **Future Integrations:** Wearable device data (fitness watches, health monitors) for automated weight and activity syncing

---

## Privacy & Security

- User data is never sold or shared outside the app
- Minimal ad exposure (post-video only); no third-party ad tracking
- All personal data (name, weight, login) is treated as private identity information
- Admins only access user data with user consent

---

## Roles & Responsibilities

**Developers / Admins**
- Manage and update the exercise library (add/remove workouts, swap videos)
- Review and approve trend-sourced exercises before they go live
- Conduct QA testing and bug fixes
- Maintain backend infrastructure (user accounts, data storage, performance)
- Ensure content appropriateness and data security

**Users**
- Create a profile and set fitness goals
- Filter and browse the workout library
- Follow along with video-guided exercises
- Log weight and track progress over time

---

## Stakeholders

- End Users
- Gym Partners
- Independent Investors / Shareholders
- Fitness Influencers (video content contributors)
- Sports Therapists (workout recommendation advisors)
- App Development Team

---

## Out of Scope

- Nutritional tracking, calorie counting, or meal planning
- Collection or sale of user data to third parties
- Displaying extensive advertisements
- Mandatory fitness metrics (no required height, weight, or body composition inputs)

---

*Built as a team project — research, metadata schema design, UI prototyping, and feature documentation completed collaboratively.*
