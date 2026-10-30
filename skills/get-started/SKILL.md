---
name: get-started
description: Set up Social Post Flow after installing the plugin. Use when the user runs setup, or asks how to start scheduling social posts with Social Post Flow.
---

# Get started with Social Post Flow

Help the user confirm their Social Post Flow account is ready to publish.

1. Call `get-user-tool` to check the account. If `has_access` is false, explain that a subscription is needed and share the returned `checkout_url`.
2. Call `list-profiles-tool` to show the connected social profiles, grouped by network.
   - If no profiles are connected, tell the user to connect one at https://app.socialpostflow.com, then try again.
   - If a profile has `connected: false`, show its `failure_reason` and explain it must be reconnected in the web app before it can publish.
3. Ask the user's timezone if it isn't clear, as scheduled times depend on it.
4. Suggest a first step, such as drafting a post for one of their profiles. Don't create or publish anything during setup.
