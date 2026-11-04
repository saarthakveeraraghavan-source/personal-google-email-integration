# Personal Inbox Assistant

Informational website for a personal, self-hosted n8n Gmail integration. The Google Cloud project should remain named `Personal`; the OAuth display name should be `Personal Inbox Assistant`.

## Website status

The original website has been reviewed locally. Publication of the HTML pages is pending confirmation of the owner's actual workflow capabilities, external data sharing, and execution-data retention. The support contact is confirmed as saarthak.veeraraghavan@gmail.com.

## Free GitHub Pages deployment

Use this existing public repository, without creating a duplicate:
https://github.com/saarthakveeraraghavan-source/personal-google-email-integration

The publishing directory is the repository root, containing `index.html`, `privacy.html`, `terms.html`, and `style.css`. Keep their relative links so project-site paths work.

After the reviewed HTML files are committed, open:
https://github.com/saarthakveeraraghavan-source/personal-google-email-integration/settings/pages

Select **Deploy from a branch**, **main**, **/ (root)**, and **Save**. Ensure **Enforce HTTPS** is selected. GitHub Pages on a public repository is available with GitHub Free; no domain purchase, billing account, or card is needed.

Expected URLs, to be verified after deployment (these are not evidence of publication):
- Home: https://saarthakveeraraghavan-source.github.io/personal-google-email-integration/
- Privacy: https://saarthakveeraraghavan-source.github.io/personal-google-email-integration/privacy.html
- Terms: https://saarthakveeraraghavan-source.github.io/personal-google-email-integration/terms.html
- Stylesheet: https://saarthakveeraraghavan-source.github.io/personal-google-email-integration/style.css

## Google OAuth

Check the selected Cloud project before changing settings. Preserve the project name `Personal`. Use the same application identity and working URLs in Google Auth Platform > Branding. Set the monitored support address and developer contact. The candidate authorized domain is `saarthakveeraraghavan-source.github.io` (no scheme or path); acceptance must be checked in Google Console.

For Search Console, an HTML file or HTML meta tag can verify a URL-prefix property. Use the exact property URL and verification location shown by Google. A project-path property does not establish ownership of the whole host, and URL-prefix verification does not guarantee OAuth authorized-domain or branding acceptance. Do not claim to own `github.io`.

Personal-use applications may qualify for an exception to sensitive/restricted scope verification. Publishing status **In production**, brand verification, scope verification, and Search Console ownership verification are separate states. Confirm the actual publishing status on Google Auth Platform > Audience. Do not submit a formal verification request unnecessarily.

Choose the narrowest scopes required by the actual workflows. Reading/searching messages generally uses `gmail.readonly`; sending uses `gmail.send`; drafts use `gmail.compose` (which also permits sending); message changes generally use `gmail.modify`. Review the scopes requested by the n8n credential itself: listing fewer scopes in Google Console does not narrow a credential's authorization request. Avoid full `https://mail.google.com/` access unless immediate permanent deletion is truly needed.

After the status is confirmed as In production, reconnect the existing n8n Google OAuth credential to request fresh offline access. A refresh token issued during Testing is subject to Google's seven-day rule for Gmail scopes. Production refresh tokens can still expire or be revoked; they are not guaranteed permanent. Keep the existing local callback URL, and do not publish the n8n dashboard, Ollama API, credentials, or tokens. Validate with a read-only operation such as listing Gmail labels rather than sending or modifying mail.

## Privacy and repository safety

Only public website assets belong in this repository. Never commit OAuth client secrets, access or refresh tokens, n8n databases, workflow exports containing personal data, execution logs, email contents, or local infrastructure configuration. Revoking OAuth access does not automatically delete stored local workflow history. Privacy disclosures must match enabled workflows before use.

## Official references

- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
- https://support.google.com/cloud/answer/15549049
- https://support.google.com/cloud/answer/15549945
- https://support.google.com/webmasters/answer/9008080
- https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification
- https://developers.google.com/workspace/gmail/api/auth/scopes
