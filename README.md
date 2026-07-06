# MatSense AI

MatSense AI is a publish-ready demo for a martial arts video analysis app. It supports Boxing, Muay Thai, Brazilian Jiu-Jitsu, and MMA workflows with upload handling, simulated coach feedback, plan limits, recent analysis history, and paid-plan positioning.

## Run Locally

```bash
npm start
```

Then open:

```text
http://127.0.0.1:4174/
```

## Current Demo Features

- Training video upload UI
- Discipline selection
- Skill level and focus selection
- API-backed analysis request flow
- Timestamped coaching notes
- Suggested drills
- Free-plan usage limit
- Recent analysis history saved in the browser
- Free, Plus, and Gym pricing section

## What The API Does Today

`POST /api/analyze` accepts multipart form data:

- `video`
- `discipline`
- `skillLevel`
- `focus`

It returns structured feedback from a local discipline playbook. This is intentionally shaped like the real AI response the production app would use.

## Production Upgrade Path

1. Store uploads in cloud object storage.
2. Extract frames and pose landmarks from each video.
3. Run discipline-specific movement analysis.
4. Use an AI model to turn detected issues into coach-quality feedback.
5. Add authentication, subscriptions, and gym/team accounts.

## Publish Notes

This demo can be deployed to any Node host that runs `npm start`. For a static-only host, the frontend will still work, but it will use the browser fallback analysis instead of the local API.

## Fastest Upload

Use any Node web host and set:

- Build command: `npm install`
- Start command: `npm start`
- Health check: `/api/health`

Good quick hosts: Render, Railway, Fly.io, Heroku-compatible hosts, or any VPS with Node 18+.
