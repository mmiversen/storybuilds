# storybuilds
# Take My Meeting - PTO Coverage Workflow

## Overview
This workflow allows team members to request coverage for meetings while they're on PTO. It automatically:
- Pulls calendar events during selected PTO dates
- Identifies available team members in the same timezone
- Posts a Slack message with claim buttons for each meeting
- Updates messages in real time when meetings are claimed
- Records who took what, when, and from whom

## Setup Instructions

### 1. Required Credentials
- **Slack Bot Token**: Create a Slack app with the following scopes:
  - `channels:read`, `groups:read`, `im:read`, `mpim:read`
  - `users.profile:read`
  - `users:read.email`
  - `chat:write`
- **Google Calendar API**: Create credentials with `https://www.googleapis.com/auth/calendar.readonly` scope

### 2. Record Types
Create two record types in Tines:

#### Team Members Record Type
Fields:
- `real_name` (Text)
- `email` (Text)
- `user_id` (Text)
- `dm_id` (Text)
- `Location Area` (Text)

#### PTO Meeting Record Type
Fields:
- `meeting_id` (Text)
- `record_type` (Text)
- `action_id` (Text)
- `slack_channel_id` (Text)
- `slack_message_ts` (Text)
- `submitter_email` (Text)
- `status` (Text)
- `meeting_details_title` (Text)
- `meeting_details_date` (Timestamp)
- `meeting_details_calendar_event_URL` (Text)
- `posted_at` (Text)
- `claimed_by` (Text)
- `claimed_at_ts` (Text)
- `reminders_count` (Number)
- `last_reminder_at` (Text)
- `submitter_location` (Text)
- `submitter_time_off` (Text)
- `run_id` (Text)
- `meeting_details_vitally` (Text)
- `meeting_details_description` (Text)
- `message_url` (Text)

### 3. Slack Channels
- Create a channel for PTO coverage requests
- Note the channel ID for configuration

### 4. Workflow Configuration
Replace the following placeholders in the workflow:
- All credential references (`CREDENTIAL.your_*`)
- Channel IDs (`YOUR_*_CHANNEL_ID`)
- Webhook path and secret
- Record type IDs
- Record field IDs

### 5. Customization
- Update form text and messaging to match your organization's terminology
- Customize timezone groupings in the workflow if needed
- Update any references to "Team Member" to match your organization's role names
