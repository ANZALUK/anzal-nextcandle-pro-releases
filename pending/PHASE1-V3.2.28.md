# Ferix Software Pro V2 — USER Phase 1 V3.2.28

Status: **PENDING WINDOWS QA — DO NOT PROMOTE TO update.json YET**

## Candidate
- Installer: `Ferix.Software.Pro.V2.USER.Setup.PHASE1-V3.2.28.exe`
- SHA256: `e4c7f13c27b8f8cef4e6b5ba99b3ade0dfeabd833a01352c9ea2dd1f9a18f828`
- Platform: Windows 10/11 x64

## Phase 1 changes
- Supported Windows device list updated; unsupported platforms shown as Coming Soon.
- Existing one-device licensing preserved.
- Start Trading requires automatic live Quotex Trade ID verification before signals start.
- Trade ID is read from the live Quotex page through the existing Chrome DevTools connection, without fixed screen coordinates/OCR.
- A changed Trade ID stops the current trading session; fifth confirmed mismatch blocks the account/license.
- Trade ID is rechecked during trading; temporary inability to verify pauses signals.
- Ferix Quotex uses a dedicated isolated Chrome profile; stale session data is cleared when the Ferix trading session closes.
- Ferix scanner and Ferix-owned Quotex window remain lifecycle-linked.
- Central API target: `https://ferixsoftware.pro`.

## Hostinger
Core Phase-1 gating and block-at-five use the existing backend. Non-blocking Admin alerts for warnings 1–4 require a small backend extension in Phase 2 because the current security-event endpoint accepts BLOCK only.

## QA before promotion
1. Install on Windows 10/11 x64.
2. Confirm normal registration/login/license flow.
3. Confirm approved Trade ID opens signals.
4. Confirm wrong Trade ID stops trading and increments warnings.
5. Confirm fifth confirmed mismatch blocks access.
6. Confirm closing Ferix closes the Ferix-owned Quotex session.
7. Confirm Defender/SmartScreen behavior.
