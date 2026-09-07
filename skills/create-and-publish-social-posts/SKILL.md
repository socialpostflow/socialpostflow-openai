---
name: create-and-publish-social-posts
description: Create one or more Social Post Flow posts, including immediate publishing, scheduled posts, and queue placement. Use when the user asks to publish, schedule, queue, or bulk-plan social content.
---

# Create and publish social posts

Use Social Post Flow to create posts for the user's connected profiles.

## Choose profiles and format

- Call `list_profiles` before creating posts. Use the returned profile IDs; do not guess them.
- If the requested account, platform, or post format is unclear, ask before creating anything.
- Let Social Post Flow validate provider-specific compatibility. Do not promise that a format is supported until the selected profiles have been checked.
- `media_urls` must be publicly accessible URLs. Do not claim that a local attachment has been uploaded; ask the user for a public URL when one is required.

## Confirm every write

Prepare a concise review that includes the target profiles, post text or caption, any link, first comment, media URLs, and timing.

- For `immediate`, state plainly that this will publish publicly now and get explicit confirmation immediately before calling the tool.
- For `scheduled`, `queue_start`, or `queue_end`, get explicit confirmation before creating the post because it changes the user's calendar.
- Drafting, suggesting copy, or discussing a plan is not confirmation.

## Create posts

- Use `create_post` for one content item and `create_bulk_posts` only when multiple independent items are ready and confirmed.
- A scheduled post requires a future ISO 8601 `scheduled_at` value. Interpret ambiguous dates in the user's stated timezone; otherwise ask.
- A link post needs `url`. Image, story, pin, and TikTok post types need `media_urls`. Do not combine a regular link post with media URLs.
- For a bulk request, keep each item complete and check the `errors` response as well as `data`. Report partial successes accurately.

After a successful write, identify the created post IDs, destination profiles, and resulting status. If immediate publishing is still processing, say so rather than claiming it has already appeared publicly.
