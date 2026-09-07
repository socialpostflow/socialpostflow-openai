---
name: review-social-posting
description: Review Social Post Flow profiles, posting status, scheduled content, published content, and failures without changing anything. Use when the user asks for a calendar, status report, or posting analysis.
---

# Review social posting

Use the read-only Social Post Flow tools to answer questions about connected profiles and posts.

- Start with `list_profiles` when the requested accounts are unclear or when checking which formats are available.
- Use `list_posts` with the narrowest useful status, profile, ordering, and pagination filters. Use `get_post` for a specific item.
- Treat `failed` posts as failures unless the response provides a public post URL or another clear success signal. Include the returned failure reason without inventing a cause.
- Summarize dates in the user's timezone where it is known. State the timezone when it affects a scheduling answer.
- This workflow is read-only. Do not create, update, publish, or delete posts unless the user explicitly asks to do so in a later request.
