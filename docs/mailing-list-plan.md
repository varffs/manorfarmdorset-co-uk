# Mailing list: future plan

Status: **not started**. Mailing list signup removed from the home page on 2026-11-03.

## Background

The home page had an embedded Mailchimp signup form. By November 2026 the
Mailchimp account/audience no longer existed: the form's action URL
(`manorfarmdorset.us7.list-manage.com/subscribe/post?u=bacb0b19c0ff0b04e7abd3162&id=2e6fa80c04`)
returned Mailchimp's "404: Page Not Found", so every signup silently failed.
The form, its copy and its CSS were removed rather than left broken.

## Decision

Replace Mailchimp with a **Google Form** on the farm's Google Workspace account.
Signups land in a Google Sheet. Updates are sent by hand from the farm Gmail
(BCC). No third-party account to keep alive, no free-tier limits.

## Steps

1. At forms.google.com, signed in to the farm Workspace account, create a blank
   form, e.g. "Manor Farm mailing list".
2. Questions (matching the old Mailchimp form):
   - **Email**: short answer, required, response validation "Text → Email"
   - **First name**, **Last name**: short answer, optional
   - **Interests**: checkboxes "Meat sales" and "Farm events", required
3. **Settings → Responses: turn OFF "Restrict to users in [domain]".**
   Workspace enables it by default, which would block the public from signing up.
   Set "Collect email addresses" to "Do not collect" (the Email question covers it).
4. Responses tab → "Link to Sheets".
5. Send → link tab → copy the URL.
6. On the home page, add a sign-up button (styled to match the site, not an
   embedded iframe) linking to the form, and restore the copy below.
7. Fill in `privacy.html` (currently a stub of headings) with what is collected,
   why, where it is stored (Google), and how to be removed. Link it near the button.

## Copy to restore

Removed from the end of the home page `<article>`:

> We plan to run informal farm guided walks of the farm. Please sign up below to be on our mailing list.

Old form heading:

> Sign up to our mailing list for farm walks and product updates

(Consider tightening: "informal farm guided walks of the farm" repeats "farm".)
