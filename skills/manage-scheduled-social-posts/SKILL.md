---
name: manage-scheduled-social-posts
description: Review, edit, reschedule, or cancel Social Post Flow scheduled posts. Use when the user wants to change a social-media calendar or remove a scheduled post.
---

# Manage scheduled social posts

Use Social Post Flow to inspect and manage existing posts.

## Find the post first

- Use `list-posts-tool` to find a post when the user gives a date, profile, status, or description rather than a post ID.
- Use `get-post-tool` before changing or deleting a post so the user can review the exact current content and timing.
- Only posts whose status is `scheduled` can be updated or deleted. Explain this constraint rather than attempting an unavailable change.

## Confirm edits and cancellation

Show the affected profile, the existing schedule, and the complete proposed replacement before calling `update-post-tool`.

- Updating a post requires its complete payload, including profile IDs. Preserve values the user did not ask to change.
- If an edit changes the schedule to `immediate`, say that it will publish publicly now and obtain explicit confirmation immediately before the tool call.
- Before `delete-post-tool`, name the post, profile, and scheduled time, and obtain explicit confirmation. Deletion cancels the scheduled post.

Report the resulting status and post ID after a successful change. Do not state that a cancelled or rescheduled post remains active.
