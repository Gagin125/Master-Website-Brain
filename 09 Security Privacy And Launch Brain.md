# Security, Privacy, And Launch Brain

This note distills three independent security/privacy launch reports into one reusable checklist for websites, web apps, SaaS, AI apps, and mobile apps.

Use this note as a launch-safety layer for future projects. It is not a replacement for legal advice, a penetration test, or platform-specific review, but it prevents the most common beginner and AI-built product failures.

## Sources Reviewed

- ChatGPT report: `Universal Application Security Research Report.docx`
- Codex report: `security-privacy-launch-knowledge-base.md`
- Gemini report: pasted security/privacy/compliance knowledge base

## Strongest Shared Conclusion

A working demo is not the same as a launch-ready product.

The recurring failure pattern is:

- The frontend looks complete, but the backend is not enforcing access.
- Authentication exists, but authorization is weak.
- API calls work, but abuse controls and rate limits are missing.
- Privacy text exists, but it does not match the real product.
- Store/app declarations are filled late and often inaccurately.
- AI tools are connected before prompt injection, cost abuse, and unsafe actions are controlled.

## Broad Agreement Across All Three Reports

All three reports agree on these fundamentals:

- Never trust the frontend as a security boundary.
- Enforce authorization on the server, database, storage, and API layers.
- Keep secrets out of Git, frontend bundles, screenshots, logs, and public files.
- If a secret was committed, rotate it. Deleting it from the visible file is not enough.
- Use mature auth providers or libraries unless there is a strong reason not to.
- Rate-limit auth, forms, expensive endpoints, AI endpoints, uploads, payments, and search.
- Use parameterized queries or ORM-safe APIs. Input validation alone is not SQL injection protection.
- Protect against IDOR/BOLA by checking object ownership on every object ID, slug, file ID, tenant ID, project ID, invoice ID, booking ID, etc.
- Enable and test RLS/security rules where the database/storage is exposed to clients.
- Do not casually log tokens, passwords, payment data, secrets, session IDs, or sensitive PII.
- Use HTTPS/TLS everywhere.
- For mobile apps with account creation, account deletion support is a platform requirement.
- Privacy policies, cookie consent, App Store privacy labels, and Google Play Data safety forms must match the real product behavior.
- AI apps need specific controls for prompt injection, output validation, tool permissions, cost limits, and untrusted retrieved content.
- SEO/traffic launch advice is useful, but it is not security.

## Contradictions And Nuance

There were no serious contradictions between the three reports. The differences are mostly about priority, scope, and legal precision.

### 1. "Production checklist" vs beginner reality

Some advice includes enterprise-grade controls such as chaos engineering, multi-region disaster recovery, SOC 2 readiness, advanced anomaly detection, and formal tabletop exercises.

Resolution:

- These are real security maturity topics.
- They are not first-launch requirements for every small website or demo.
- Use P0/P1/P2/P3 priority so a small cafe website is not treated like a banking SaaS.

### 2. Supabase RLS "off by default"

Some content says Supabase RLS is off by default.

Resolution:

- The beginner warning is valid: verify RLS/table policies yourself.
- The exact default depends on how tables are created and the current Supabase behavior.
- Never assume "auth exists" means row isolation exists.

### 3. DMCA, arbitration, CCPA, FTC, and exact fine amounts

Some video claims frame these as universal hard rules or exact penalties.

Resolution:

- They are legally relevant, but jurisdiction-dependent.
- DMCA is mainly a US safe-harbor/takedown topic.
- Arbitration/class waivers are legal strategy, not a universal shield.
- FTC AI claims are real, but exact penalty claims should not be repeated without current legal review.
- For Lithuania/EU, GDPR, ePrivacy/cookie rules, consumer law, and the European Accessibility Act may matter more than US-specific shortcuts.

### 4. Cookie consent

Some advice says "add a cookie banner."

Resolution:

- A banner does not fix tracking by itself.
- The real task is to avoid non-essential tracking before consent where required, describe purposes accurately, allow refusal, and store consent choices.
- Strictly necessary cookies usually do not need consent, but still need disclosure.

### 5. LocalStorage vs cookies

All reports agree localStorage is risky for sensitive auth tokens because XSS can read it.

Resolution:

- Prefer HttpOnly, Secure, SameSite cookies or a backend-for-frontend pattern for browser sessions.
- If token storage is unavoidable, document the risk and add compensating controls.

### 6. Prompt injection

Some advice suggests delimiters or prompt separation as a fix.

Resolution:

- Delimiters help structure prompts but are not a security boundary.
- Treat prompts, RAG documents, websites, uploaded files, tool outputs, and user content as untrusted.
- Use least-privilege tools, output validation, allowlists, cost limits, and human approval for high-risk actions.

### 7. Network pinning for mobile

Network pinning can be useful, but it is not a universal V1 requirement.

Resolution:

- Use HTTPS/TLS and secure platform storage as baseline.
- Consider certificate pinning only when the threat model justifies it and the operational risk is understood.

## Priority Model

Use this to stop future AI agents from overbuilding the wrong thing.

### P0: Do Not Launch Without These

These can block launch, expose users, cause instant abuse, or fail platform review.

- No server-side authorization on private data.
- Missing object ownership checks.
- Public database/storage with private user or business data.
- Secrets in Git, frontend code, public env files, logs, or screenshots.
- Missing HTTPS on production.
- SQL injection risk from string-built queries.
- Auth tokens stored unsafely without understanding the risk.
- Admin panel protected only by hidden UI or client-side role checks.
- Payment webhook signatures not verified.
- AI keys exposed to the client.
- No rate limits on login, signup, password reset, AI, upload, payment, or expensive endpoints.
- Sensitive data logged casually.
- Mobile app has account creation but no account deletion path.
- App Store / Google Play privacy declarations do not match real SDK/data behavior.
- No privacy notice for a product collecting personal data.

### P1: Serious Launch Readiness

These should be done before real users, paid traffic, App Store/Google Play submission, or investor/client presentation.

- MFA for admin and privileged users.
- Dependency scanning and vulnerable package review.
- Basic audit logs for admin/security-sensitive actions.
- Backup and restore plan, with at least one restore test for serious products.
- Cookie/tracking consent where non-essential tracking exists.
- File upload restrictions: size, extension allowlist, signature checks where useful, generated filenames.
- Spam prevention for public forms.
- Accurate data inventory: what is collected, stored, shared, logged, deleted.
- AI prompt injection tests and cost-abuse tests.
- Store review credentials or demo access for mobile apps.
- Accessibility pass: keyboard, contrast, labels, forms, headings, alt text.

### P2: Maturity Layer

Useful after the product has users or business risk.

- Incident response runbook.
- Retention/deletion automation.
- Advanced monitoring and alerting.
- Security headers/CSP tuning.
- More formal threat model.
- Regular dependency patch cadence.
- External security review for sensitive products.
- Fine-grained admin roles and admin action exports.

### P3: Advanced / Conditional

Do not force these onto every small product.

- SOC 2 readiness.
- Formal SBOM/provenance pipeline.
- Enterprise SSO.
- Multi-region disaster recovery.
- Chaos engineering.
- Advanced anomaly detection.
- External penetration test for low-risk brochure sites.
- Certificate pinning unless threat model needs it.

## Universal Website And App Checklist

### Architecture

- Define who can do what before building UI.
- Identify public, user-private, admin-only, paid, and expensive actions.
- Decide where each security boundary lives: backend, database, storage, edge function, server action, cloud rule.
- Keep the frontend as an experience layer, not an authority layer.

### Authentication

- Prefer proven auth providers/libraries.
- Add login throttling.
- Use strong password reset flows with single-use, time-limited tokens.
- Verify email where email ownership matters.
- Require MFA for admins.
- Do not treat email as a strong second factor by itself.

### Sessions

- Prefer HttpOnly, Secure, SameSite cookies for browser sessions.
- Avoid localStorage/sessionStorage for sensitive tokens.
- Invalidate sessions on logout, password change, major risk events, and privilege changes where appropriate.
- Keep privileged sessions shorter.

### Authorization

- Check every endpoint and server action.
- Check object ownership for every user-controlled ID.
- Check tenant ownership for SaaS and multi-location businesses.
- Check admin/function-level permissions separately from login.
- Test by changing IDs in URLs and network requests.

### Database And Storage

- Use least-privilege database credentials.
- Enable and test RLS/security rules where clients can access data directly.
- Make storage buckets private unless intentionally public.
- Use signed URLs for private files.
- Test cross-user read/write attempts.

### API And Abuse Controls

- Rate-limit login, signup, password reset, email resend, forms, uploads, AI, payments, search, and scraping-sensitive endpoints.
- Add request size limits.
- Add quotas for expensive operations.
- Add per-IP, per-account, per-tenant, and per-endpoint limits when useful.
- Use backoff/circuit breakers for expensive third-party APIs.

### Input And Injection

- Validate input server-side.
- Use parameterized queries/prepared statements/ORM-safe query APIs.
- Do not build SQL/NoSQL queries by string concatenation.
- Encode output based on context when rendering user content.
- Reject oversized, malformed, or unexpected input.

### Secrets

- `.env` is fine for local development, but secrets must not be committed.
- Use production secret managers/environment settings for deployed apps.
- Scope keys narrowly.
- Rotate secrets if exposed.
- Remember that Git history may still contain deleted secrets.

### Logging And Monitoring

- Log security events: auth failures, authorization failures, admin actions, payment webhook failures, file upload violations, AI abuse events.
- Do not log passwords, raw tokens, session IDs, DB URLs, API keys, card data, or unnecessary sensitive PII.
- Redact or hash sensitive identifiers when possible.
- Alert on auth spikes, 5xx spikes, AI cost spikes, payment failures, and unusual traffic.

### Payments

- Prefer hosted/tokenized payment flows.
- Never store raw card data unless absolutely necessary and properly scoped.
- Verify webhook signatures.
- Recalculate prices server-side.
- Make payment state transitions idempotent.

### File Uploads And UGC

- Allowlist file types.
- Enforce size limits.
- Rename files to generated names.
- Do not store uploads in executable paths.
- Treat uploaded content as untrusted.
- Add report/block/takedown flows if users can publish content.

### Privacy

- Make a data map before writing privacy copy.
- Know what data is collected, why, where it is stored, who receives it, how long it stays, and how deletion works.
- Privacy policy must match real code, SDKs, analytics, forms, CRM, email tools, payment tools, and AI vendors.
- Add account deletion if accounts exist, especially for mobile apps.
- Do not collect data just because a tool makes it easy.

### Cookies And Tracking

- Separate strictly necessary cookies from analytics/marketing cookies.
- For EU/UK style consent, do not load non-essential tracking before valid consent.
- Provide an actual reject option where required.
- Store consent choice.
- Do not use "by using this site you agree" as a consent replacement for non-essential tracking.

### Accessibility

- Use semantic HTML.
- Maintain heading order.
- Ensure keyboard navigation works.
- Use labels for form controls.
- Use meaningful alt text where images communicate content.
- Meet contrast requirements.
- Do not rely on color alone for meaning.

## AI App Checklist

Use this when the product calls an LLM, generates content, uses RAG, or lets AI tools take actions.

- Keep AI API keys server-side.
- Rate-limit AI endpoints aggressively.
- Add per-user cost quotas.
- Treat prompts, retrieved documents, URLs, uploaded files, and tool outputs as untrusted.
- Do not let user content override system instructions.
- Delimiters are helpful, but not enough.
- Validate model outputs before using them in code, SQL, shell, emails, payments, account actions, or moderation decisions.
- Give tools the least privilege possible.
- Require human approval for destructive, financial, legal, account, or external-send actions.
- Do not claim "AI secure" or "AI compliant" unless the product actually supports that claim.
- Add abuse logging without storing unnecessary private prompts.

## Mobile / App Store / Google Play Checklist

Use this when shipping native apps, wrapped web apps, or store-published products.

- Provide a privacy policy URL.
- Ensure privacy labels/Data safety forms match real data collection, SDKs, analytics, ads, crash reporting, and sharing.
- Provide account deletion if users can create accounts.
- Provide demo credentials or review access if login is required.
- Request only necessary permissions.
- Explain permissions clearly.
- Use secure platform storage such as Keychain/Keystore for sensitive local data.
- Test offline states, permission denial, and account deletion.
- Check UGC requirements if users can post, message, upload, comment, or share.
- Check AI-generated content declarations if applicable.
- Do not rely on App Store/Google Play review as a security audit.

## Product-Type Notes

### Static Marketing Website

Baseline:

- HTTPS.
- Secure hosting.
- Minimal scripts.
- Contact form spam/rate protection.
- Privacy policy if collecting personal data.
- Cookie consent if using non-essential tracking.
- Accessibility basics.
- No exposed admin/CMS credentials.

Usually not needed:

- Complex auth.
- SOC 2.
- Multi-region DR.
- Advanced anomaly detection.

### Local Business Website

Add:

- Accurate contact info.
- Google Business Profile alignment.
- Reviews and trust signals.
- Clear privacy/cookie behavior.
- Form spam protection.
- Performance/image optimization.

Security risk is usually lower, but reputation risk is high.

### Booking / Reservation Site

Add:

- Booking ownership checks.
- Anti-spam and rate limits.
- Email/SMS abuse controls.
- Privacy notice for reservation data.
- Safe admin access.
- Webhook verification if using third-party booking/payment tools.

### Ecommerce

Add:

- Hosted payments.
- Webhook signature verification.
- Server-side price calculations.
- Order ownership checks.
- Return/refund policy clarity.
- Inventory/rate abuse controls.

### SaaS / Logged-In Web App

Add:

- Tenant isolation.
- Role matrix.
- Audit logs.
- Admin MFA.
- Backup/restore testing.
- Account deletion/export.
- Dependency scanning.
- Incident response basics.

### AI Tool

Add:

- AI cost limits.
- Prompt injection tests.
- Tool permission model.
- Data retention policy for prompts/uploads.
- Output safety checks.
- Vendor/model disclosure where appropriate.

## Test Recipes For Future Projects

Run these before launch.

### Direct URL / IDOR Test

- Log in as User A.
- Copy a private URL or API request.
- Change `userId`, `projectId`, `bookingId`, `invoiceId`, `fileId`, or slug to User B's value.
- Expected result: denied.

### Logout Test

- Open private page.
- Log out.
- Press back/refresh/retry API call.
- Expected result: denied or redirected.

### Client Tamper Test

- Use DevTools to edit role, local state, hidden buttons, disabled fields, and request payloads.
- Expected result: backend ignores unauthorized changes.

### Rate Limit Test

- Try repeated login, signup, password reset, form submission, AI call, upload, or payment session creation.
- Expected result: throttled.

### Secret Exposure Test

- Search repo, built JS, network responses, source maps, and logs for secrets.
- Expected result: no live secrets.

### Logging Test

- Trigger auth, payment, AI, and upload flows.
- Inspect logs.
- Expected result: useful events, no raw tokens/passwords/card data/secrets/unnecessary PII.

### Privacy Reality Test

- Compare privacy policy/store labels to actual scripts, SDKs, analytics, forms, CRM, payment tools, AI vendors, and logs.
- Expected result: no mismatches.

## AI Agent Prompt Insert

Use this when asking an AI agent to build or audit an app.

```text
Build this as production-oriented software, not only a demo.

Security rules:
- Never trust frontend-only access control.
- Keep secrets out of frontend code, Git, logs, and screenshots.
- Enforce server-side authorization for every private action.
- Add object ownership checks for all IDs/slugs/files/bookings/invoices/projects.
- Use parameterized queries or ORM-safe APIs.
- Add rate limits to auth, forms, uploads, AI, payments, and expensive endpoints.
- Use secure sessions; avoid localStorage for sensitive bearer tokens unless explicitly justified.
- Verify payment webhooks.
- Redact sensitive logs.
- Add privacy/account deletion/cookie/store requirements where relevant.
- For AI features, treat prompts, RAG docs, uploaded files, and tool outputs as untrusted.

Before finishing, output:
- P0 launch blockers
- P1 serious launch items
- Security assumptions
- Env var inventory
- Endpoint inventory
- Auth/authz matrix
- Manual abuse test checklist
- Remaining risks
```

## Rules To Remember Next Time

- Do not let "AI built it" become an excuse for weak backend boundaries.
- Do not add enterprise checklists blindly. Prioritize by real product risk.
- Security should be designed into the first architecture, not added as a panic layer before launch.
- For demos shown to business owners, do not fake privacy/security maturity. Keep promises accurate.
- If handling accounts, payments, uploads, AI tools, health/finance/children data, or app-store publishing, raise the security bar immediately.
- Legal claims need legal review. Do not trust viral videos for exact fines, arbitration protection, or jurisdiction-specific compliance.
- Good security is mostly boring: correct access, limited secrets, controlled abuse, truthful privacy, safe logs, tested failures.

