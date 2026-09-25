# QA Bug to Regression Test — Privacy Policy

Last updated: September 25, 2026

Developer: Orhan Eren Kara

QA Bug to Regression Test is a Chrome extension designed to help software testers record manual bug reproduction sessions and turn them into structured bug reports and editable Playwright regression-test drafts.

## Data processed by the extension

The extension may process the following data when you use its features:

- The URL of the page where a bug recording session is started.
- Recorded user interactions such as supported clicks, form input, selections, and navigation events.
- User-provided Bug title, Expected Result, and Actual Result text.
- Assertions added during a recording session.
- Technical context related to the recorded page, such as supported element labels, text, roles, placeholders, and other locator metadata.
- Context diagnostics such as iframe presence/focus, popup or new-tab events, recording-tab changes, and supported navigation changes.
- Optional screenshot evidence captured only when the user explicitly requests it.
- Extension settings, including the selected interface language.
- Session timestamps and other metadata required to restore the active or most recently completed session.

The extension does not intentionally collect general browsing history outside the current QA recording workflow.

## Local storage

The active session, the most recently completed session, user settings, recorded actions, assertions, diagnostics, bug details, and optional screenshot evidence are stored locally in the browser using `chrome.storage.local`.

This version of the extension does not use a backend service or cloud synchronization for session data.

Local session data may remain in browser storage until it is replaced, cleared through browser or extension storage controls, or the extension is removed.

## Website access

The extension declares optional access to HTTP and HTTPS websites because QA sessions may be started on different sites.

Site access is requested when the user starts a recording session on a selected website. The extension uses this access to inject the recorder into the selected page and observe supported interactions required for the QA workflow.

The extension does not continuously inject the recorder into every website and does not intentionally monitor unrelated browsing activity.

Chrome may retain previously granted site access until the user revokes it through browser controls.

## Recorded interactions

During an active recording session, the extension may process supported interactions such as:

- Clicks
- Form input
- Select changes
- Supported navigation events
- Assertions added by the user

Unsupported or ambiguous interactions may be skipped or flagged for manual review.

The extension may also detect context-level events such as iframe interaction, popup or new-tab opening, or cross-origin navigation in order to warn the user that parts of the flow may require manual review.

## Sensitive data and redaction

The extension uses rule-based detection and redaction for recognized sensitive values.

Examples may include:

- Password fields
- API keys
- Tokens
- Authorization values
- Other recognized credential-like values

Recognized sensitive values may be replaced with markers such as:

`[REDACTED]`

or

`REPLACE_WITH_TEST_VALUE`

in generated artifacts.

Sensitive-data detection is not exhaustive. Unknown secret formats, user-entered free text, page text, URL paths, unsupported URL structures, or other content may still contain sensitive information.

Users should review generated bug reports and Playwright drafts before sharing or committing them.

## Screenshot evidence

Screenshots are captured only when the user explicitly requests screenshot evidence.

Screenshot pixels are not automatically inspected or redacted.

A screenshot may contain sensitive information that is visible on the page at the time of capture.

The extension displays reminders asking users to review screenshot evidence before sharing or attaching it to a bug report.

Screenshot evidence is stored locally as part of the current session and can be downloaded separately as an image file.

## Generated Playwright tests

Generated Playwright output is an editable draft.

The extension does not guarantee that generated tests will run successfully without review.

Complex UI patterns, ambiguous locators, unsupported interactions, asynchronous behavior, iframe content, popup flows, or other application-specific behavior may require manual Playwright changes.

Sensitive test values are not automatically resolved from secret-management systems. Placeholder values must be replaced according to the user's own secure test-data strategy before running the test.

## Generated bug reports

Bug reports are generated from the recorded session and may include:

- Bug title
- Environment URL
- Steps to reproduce
- Expected Result
- Actual Result
- Assertions
- Screenshot evidence references
- Technical notes
- Context warnings

Reports can be generated in English or Turkish depending on the selected extension language.

User-entered text is not automatically translated.

## Data sharing

The extension does not sell user data.

The extension does not use session data for advertising, credit eligibility, financial assessment, profiling, or purposes unrelated to the extension's QA workflow.

This version does not intentionally send recorded session data, bug reports, Playwright drafts, or screenshots to a developer-operated backend or cloud service.

Downloaded files, clipboard content, and any data manually shared by the user outside the extension are outside the extension's control.

## Analytics and tracking

The extension does not include developer-operated analytics, advertising trackers, or behavioral telemetry in the current version.

## Permissions

The extension uses the following Chrome permissions:

### sidePanel

Used to display the QA recording and generation workflow alongside the webpage being tested.

### storage

Used to store the active session, most recently completed session, settings, actions, assertions, bug details, diagnostics, and optional screenshot evidence locally in the browser.

### tabs

Used to identify the recording tab, observe supported navigation changes, detect popup or new-tab context changes, and verify that screenshot capture occurs on the correct tab.

### scripting

Used to inject the recorder into the website where the user explicitly starts a bug recording session.

### activeTab

Used for user-initiated screenshot capture and other actions that require access to the currently active recording tab.

### Optional host permissions

The extension declares optional access to:

- `http://*/*`
- `https://*/*`

These permissions allow the extension to request access to the website where the user chooses to start a QA recording session.

The extension does not request permanent access to all supported websites at installation time.

## Data retention and deletion

The extension currently stores:

- The active session
- The most recently completed session
- User settings

These remain in local browser storage according to the extension's current storage behavior.

Users can remove the extension or clear extension storage through Chrome to remove locally stored extension data.

Files that users have downloaded, copied, or shared separately are not automatically deleted by the extension.

## Privacy limitations

The extension is designed with privacy-aware behavior, but it is not a complete data-loss prevention or secret-detection system.

In particular:

- Rule-based secret detection may not recognize every sensitive value.
- Screenshot pixels are not automatically redacted.
- User-entered text may contain sensitive information.
- Sensitive information in page content or URL paths may not always be detected.
- Generated artifacts require human review before external sharing.

The extension does not claim that all sensitive information is automatically removed.

## Chrome Web Store Limited Use

Use of information received from Chrome APIs is limited to providing and improving the extension's user-facing QA functionality.

User data is not sold or transferred for advertising, credit evaluation, or unrelated purposes.

The extension is intended to comply with Chrome Web Store User Data and Limited Use requirements.

## Contact

For privacy, data handling, or support questions:

**Email:** orhanerenkara.dev@gmail.com

© 2026 Orhan Eren Kara. All rights reserved.
