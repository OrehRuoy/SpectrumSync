# Privacy Policy for Spectrum Sync

**Effective date:** June 16, 2026  
**Last updated:** June 16, 2026

---

## 1. Introduction

This Privacy Policy describes how **Spectrum Sync** ("**App**," "**we**," "**us**," or "**our**") collects, uses, stores, shares, and protects information when you install or use our Android application.

Spectrum Sync is a social language coaching tool designed to help neurodivergent users communicate more confidently in text-based conversations. The App includes a settings and onboarding experience and an optional **Spectrum Sync Coach** accessibility service that reads text you type in supported apps to provide real-time coaching feedback.

**Developer / Data Controller:** Brock Hall  
**Contact email:** [hallanhype@gmail.com](mailto:hallanhype@gmail.com)  
**Android application ID:** `com.spectrumsync.keyboard`  
**Privacy policy URL:** https://orehruoy.github.io/SpectrumSync/privacy-policy.html

By downloading, installing, or using Spectrum Sync, you agree to this Privacy Policy. If you do not agree, do not use the App.

---

## 2. Summary (Plain Language)

- Spectrum Sync **does not require you to create an account**.
- The coaching feature works only if you **voluntarily enable** the Spectrum Sync Coach accessibility service in Android settings.
- When coaching is active, the App may read **text you type in editable fields** in other apps so it can analyze tone and suggest improvements.
- The App **does not read password fields**, **does not read most personal-data forms**, and **does not coach in blocked sensitive apps** (such as banking, payment, tax, healthcare, and password-manager apps).
- AI analysis is performed **on your device when possible** (Gemini Nano). If on-device AI is unavailable, **limited text may be sent to Google’s cloud AI** through Firebase AI Logic.
- We **do not sell your personal information**.
- We **do not use third-party advertising networks**.
- We **do not include third-party analytics or crash reporting SDKs** in the App at this time.
- Most App data stays **on your device**. Subscription status is handled by **Google Play**.

---

## 3. Information We Collect

We collect or process the following categories of information.

### 3.1 Information You Provide Directly

#### A. Text you type (User Content)

When the Spectrum Sync Coach accessibility service is enabled and coaching is not paused, the App may access text from the editable field you are currently typing in, including:

- Message drafts in messaging, email, and social apps
- Notes and other conversational text in supported apps
- The current sentence or line being composed (not necessarily your entire message history)

This text is used **only** to provide coaching feedback (tone warnings, explanations, and suggested rewrites).

We apply automated safeguards to **avoid reading or analyzing** text when:

- The field is marked as a password field
- The field appears to be a search box, address form, or personal-data form (for example: name, email address, phone number, payment card, OTP, SSN, date of birth, bank account, tax ID, verification code)
- The field is marked with Android `no_suggestions` / similar signals
- The foreground app is on our sensitive-app blocklist (banking, payment, crypto, tax, healthcare, password managers, and similar categories)
- You have blocked the app in Spectrum Sync settings
- You have paused coaching

#### B. App settings and preferences

Stored locally on your device in `social_coach_settings.json`:

- AI sensitivity / aggression filter level
- Coaching toggles (for example bluntness filter, explain-why)
- Theme preferences (app and overlay)
- Whether coaching is paused
- Trial start timestamp
- Premium subscription active flag (synced from Google Play purchase state)
- List of apps you have manually blocked from coaching

#### C. Support communications

If you email us at [hallanhype@gmail.com](mailto:hallanhype@gmail.com), we receive the information you choose to send (such as your email address, message content, and any attachments).

### 3.2 Information Collected Automatically

#### A. Accessibility and foreground app context

When the accessibility service is enabled, the App may automatically access:

- The **package name** of the foreground application (to determine whether coaching is allowed)
- **Accessibility metadata** about the focused editable field (for example hint text, content description, view identifiers, and whether the field is a password field)
- **Window and focus events** needed to show the coaching overlay

We use this information to decide **whether coaching should run**, not to build a profile of your app usage over time.

#### B. Local usage counters (cloud AI limits)

To protect you from excessive cloud API usage and cost, the App stores local counters and timestamps on your device, including:

- Number of cloud AI requests made today
- Hourly cloud usage
- Cooldown/backoff state after failures or quota limits

These records **do not include the content of your messages**.

#### C. Subscription and billing information

Purchases, free trials, and subscription status are processed by **Google Play Billing**. Google may provide us with:

- Whether you have an active subscription or trial entitlement
- Product identifiers (for example `premium_access_monthly`)
- Purchase tokens and related billing metadata needed to verify premium access

We do **not** receive or store your full payment card number. Payment processing is handled by Google.

#### D. Device and technical information

When AI inference runs, your device and our service providers may process limited technical information such as:

- Device model and Android version
- App version
- Network connectivity status (needed for optional cloud fallback)
- Firebase / Google API request metadata required to deliver AI responses

We do not intentionally collect precise location data for coaching.

### 3.3 Information We Do Not Collect

We do **not** intentionally collect:

- Passwords, PINs, OTPs, or security codes
- Full browsing history
- Contacts, photos, microphone audio, or camera data
- SMS/read call logs (the App does not request those permissions)
- A persistent account profile on our servers
- Advertising identifiers for ad targeting

---

## 4. How We Use Information

We use information for the following purposes:

| Purpose | Examples |
|--------|----------|
| **Provide coaching** | Analyze typed text and show tone feedback, warnings, and rewrite suggestions |
| **Safety and exclusions** | Detect password/sensitive fields and blocked apps so coaching does not run there |
| **Operate the App** | Save settings, themes, pause state, and blocked-app lists locally |
| **Manage subscriptions** | Verify premium access and free-trial eligibility via Google Play |
| **Limit cloud AI usage** | Enforce daily/hourly caps and cooldowns for cloud fallback requests |
| **Improve reliability** | Diagnose AI/network failures using local debug traces in development builds |
| **Respond to you** | Answer support emails |
| **Legal compliance** | Meet legal obligations and enforce our terms |

We do **not** use your typed message content for advertising or sell it to data brokers.

---

## 5. Accessibility Service Disclosure (Required)

Spectrum Sync uses an Android **AccessibilityService** named **Spectrum Sync Coach**.

### What the accessibility service can access

When enabled, it may:

- Observe text changes and focus changes in editable fields
- Read window content necessary to locate the field you are typing in
- Display a floating coaching overlay above other apps
- Insert suggested replacement text when you choose a suggestion

### Why we use it

The accessibility service is the core mechanism that lets Spectrum Sync coach you **while you use your normal keyboard** in other apps. Without it, real-time coaching cannot function.

### What we do not use it for

We do **not** use the accessibility service to:

- Log keystrokes for unrelated surveillance
- Collect data from apps you have blocked
- Read banking, payment, healthcare, or password-manager apps on our blocklist
- Access password or personal-data fields identified by our safeguards

### Your control

You can stop all accessibility-based processing at any time by:

1. Turning off **Spectrum Sync Coach** in Android **Settings → Accessibility**
2. Using **Pause coaching** inside Spectrum Sync
3. Adding apps to **Blocked apps** in Spectrum Sync settings
4. Uninstalling the App

Disabling the accessibility service does not automatically delete local settings files on your device.

---

## 6. AI Processing and Automated Decision-Making

Spectrum Sync uses artificial intelligence to analyze text and generate coaching feedback.

### On-device processing (preferred)

On supported devices, analysis may run **entirely on your device** using **Gemini Nano** through Google on-device AI components (including AICore / ML Kit where available). In this mode, your coaching text is processed locally and is **not sent to our servers**.

### Cloud fallback processing

If on-device AI is unavailable or cannot produce a valid result, the App may send **only the current sentence or line being analyzed** (trimmed to an internal length limit) to **Google’s generative AI services** through **Firebase AI Logic**, using models such as **Gemini 2.5 Flash**.

Cloud requests are subject to app-side limits, including approximate caps of:

- **25 cloud coaching requests per day** during the free trial period
- **150 cloud coaching requests per day** for active premium subscribers
- Additional hourly, interval, and cooldown limits

Cloud fallback does **not** run when coaching is paused, blocked by safeguards, or blocked by quota limits.

### Output format

AI responses are structured coaching results (status, short warning, reasoning, and suggestions). The App displays these in the overlay. Choosing a suggestion may replace text in the active field.

### No human review by default

We do not routinely have humans read your typed content. Support emails you send us are handled separately.

---

## 7. How We Share Information

We share information only as described below.

### 7.1 Service providers

| Provider | Purpose | Data involved |
|---------|---------|---------------|
| **Google Firebase / Firebase AI Logic** | On-device and cloud AI inference | Trimmed coaching text (cloud fallback only), prompts/instructions, technical request metadata |
| **Google Play / Google Play Billing** | Subscriptions, trials, purchase verification | Purchase tokens, product IDs, subscription status |
| **Google (Android platform services)** | Accessibility framework, on-device AI runtime | Text processed on-device per Google’s platform rules |

We do not authorize these providers to use your coaching text for their own advertising.

### 7.2 Legal and safety

We may disclose information if we believe in good faith that disclosure is necessary to:

- Comply with law, regulation, legal process, or governmental request
- Protect the rights, property, or safety of Brock Hall, users, or the public
- Investigate fraud, security, or technical issues

### 7.3 Business transfers

If Spectrum Sync is involved in a merger, acquisition, or asset sale, user information may transfer as part of that transaction. We will notify you where required by law.

### 7.4 We do not sell personal information

We do **not** sell or share personal information for cross-context behavioral advertising.

---

## 8. Data Retention

| Data type | Retention |
|----------|-----------|
| Local settings (`social_coach_settings.json`) | Until you change settings, clear app data, or uninstall |
| Coaching text in memory | Only while processing the current coaching request; not stored in a message history database by us |
| Cloud usage counters | Stored locally; reset according to daily/hourly logic in the App |
| Google Play purchase records | Retained by Google under Google’s policies; we retain only what is needed locally to verify premium access |
| Support emails | Retained as long as needed to respond and maintain records, unless you request deletion |

Because we do not operate user accounts on our own servers, most deletion can be accomplished on-device.

---

## 9. Data Security

We use reasonable administrative, technical, and organizational measures designed to protect information, including:

- Processing coaching text only when safeguards allow
- Preferring on-device AI when available
- Limiting cloud transmission to trimmed sentence-level text
- Using encrypted transport (HTTPS/TLS) for cloud AI requests
- Storing settings locally in the App’s private storage area

No method of transmission or storage is 100% secure. We cannot guarantee absolute security.

---

## 10. Your Choices and Rights

Depending on where you live, you may have rights regarding your personal information.

### 10.1 Controls in the App

- Enable or disable the accessibility service
- Pause coaching
- Block specific apps from coaching
- Adjust sensitivity and coaching options
- Manage or cancel subscriptions in Google Play

### 10.2 Access, deletion, correction, and portability

Because most data is stored locally on your device, you can:

- **Access / correct settings:** Open Spectrum Sync settings
- **Delete local App data:** Android **Settings → Apps → Spectrum Sync → Storage → Clear data**
- **Uninstall:** Removes the App and local App data from your device

To request help deleting information you sent us by email, contact [hallanhype@gmail.com](mailto:hallanhype@gmail.com).

### 10.3 European Economic Area (EEA), UK, and Switzerland (GDPR)

If GDPR applies, our legal bases include:

- **Consent:** Enabling the accessibility service and using coaching features
- **Contract:** Providing premium features you purchase
- **Legitimate interests:** Securing the App, preventing abuse of cloud AI, and supporting users

You may have the right to access, rectify, erase, restrict, object, and data portability, and to withdraw consent where processing is consent-based. You may lodge a complaint with your local supervisory authority.

### 10.4 California (CCPA/CPRA)

California residents may have the right to know, access, delete, and correct personal information, and to opt out of sale/sharing. As stated above, we **do not sell** personal information.

### 10.5 Response time

We will respond to verified privacy requests within the timeframes required by applicable law.

---

## 11. Permissions We Request

Spectrum Sync may request or rely on the following Android permissions and capabilities:

| Permission / capability | Why we need it |
|------------------------|----------------|
| **Accessibility Service (Spectrum Sync Coach)** | Read editable text and show coaching overlay in other apps |
| **Display over other apps / overlay window** | Show coaching pill and expanded panel |
| **Internet** | Cloud AI fallback and Google Play Billing |
| **Network state** | Detect connectivity for cloud fallback behavior |
| **Billing / in-app purchases (via Google Play)** | Premium subscriptions and free trial |
| **Post notifications (if requested by OS)** | Service-related notices where applicable |
| **Request ignore battery optimizations (optional prompt)** | Reduce risk of Android stopping the coaching service |

You can deny or revoke permissions in Android settings. Some features will not work without the accessibility service.

---

## 12. Children’s Privacy

Spectrum Sync is **not directed to children under 13** (or the minimum age required in your jurisdiction). We do not knowingly collect personal information from children.

If you believe a child has provided us information, contact [hallanhype@gmail.com](mailto:hallanhype@gmail.com) and we will take appropriate steps to delete it.

---

## 13. International Data Transfers

If you use cloud AI fallback, your coaching text and related request data may be processed on servers operated by Google in the **United States** and other countries where Google or its subprocessors operate.

Where required, we rely on appropriate safeguards such as standard contractual clauses or equivalent mechanisms provided by our service providers.

---

## 14. Third-Party Links and Services

The App may link to external resources (for example Google Play subscription management). This Privacy Policy does not apply to third-party websites or services. Review their privacy policies separately.

---

## 15. Google Play Data Safety Summary

For Google Play Console transparency, Spectrum Sync generally:

- Collects **user-provided text** for **app functionality** (coaching) when the accessibility service is enabled
- Collects **app activity / settings** locally for functionality
- Processes **purchase history / subscription status** via Google Play
- Does **not** sell data
- Uses **encryption in transit** for cloud AI requests
- Allows users to request deletion via app data clearing, uninstallation, or email contact

Actual Data Safety form answers should match your release configuration.

---

## 16. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. When we do, we will revise the **Last updated** date at the top. If changes are material, we will provide additional notice where required (for example in-app notice or updated Play Store listing).

Continued use after the effective date of an updated policy means you accept the revised policy.

---

## 17. Contact Us

If you have questions, concerns, or privacy requests, contact:

**Brock Hall**  
Email: [hallanhype@gmail.com](mailto:hallanhype@gmail.com)

We will respond as soon as reasonably possible.

---

*End of Privacy Policy*
