# Privacy and permissions checklist

Fill this in for each app plan. Mark every item **Yes**, **No**, or **TODO**.
Items marked **VERIFY** name things that change over time - confirm them
against current official platform documentation before presenting them as
fact to the user.

## 1. Location source

- [ ] The plan states where location comes from: video metadata, user input,
  or both
- [ ] The app still works when location permission is denied (for example
  manual entry only)
- [ ] Videos without any location are handled gracefully (they still appear
  in the grid, just not on the map)

## 2. Permission prompts (VERIFY all names and rules)

- [ ] Android - the runtime permission names are taken from current Android
  documentation (candidates such as `ACCESS_COARSE_LOCATION` and
  `ACCESS_FINE_LOCATION` are commonly used - **VERIFY** exact names and which
  one each feature actually requires)
- [ ] iOS - the Info.plist usage-description keys are taken from current
  Apple documentation (candidates such as `NSLocationWhenInUseUsageDescription`
  are commonly used - **VERIFY** exact key names; do not plan
  always-in-use background location for this app)
- [ ] Web - the browser Geolocation API is invoked only after a user action,
  and any secure-context or permission-policy requirements are **VERIFY**ied
  against current browser docs
- [ ] The app shows its own plain-language explanation of why location is
  needed before the system dialog appears
- [ ] Denying permission leads to a graceful fallback, not a dead end

## 3. Consent and user control

- [ ] Location is off until the user opts in; there is no silent collection
- [ ] Consent is recorded (a flag or timestamp is enough) before any
  location is stored
- [ ] The user can edit or remove a video's location later
- [ ] The user can delete a video together with its location data
- [ ] If accounts exist, the plan says where the user can review their
  stored locations

## 4. Data handling

- [ ] Only the precision the feature needs is stored (coarse or exact -
  decide deliberately and say why in the plan)
- [ ] Location is attached to recorded videos, not to the user continuously
- [ ] A retention rule exists: say when location data is deleted
- [ ] Any third-party sharing (analytics, crash reporting, map provider) is
  disclosed in the plan, or the plan states there is none
- [ ] The plan does not propose storing location history, movement trails, or
  live device position

## 5. Store and platform requirements (VERIFY - these change often)

- [ ] The app-store privacy label / data safety form will match what the app
  actually collects (**VERIFY** current Google Play and App Store
  requirements for your app)
- [ ] A privacy policy URL is planned if the store, map SDK terms, or the
  platform requires one (**VERIFY**)
- [ ] The map provider's terms of service are checked for attribution and
  quota obligations (**VERIFY** current terms and free-tier limits)

## 6. Involving a professional

- This checklist is engineering guidance only. It is **not legal advice**.
- Privacy laws (for example GDPR or CCPA-style rules) depend on where users
  live and what data is stored. Have a qualified lawyer confirm obligations
  for the app's audience.
- In the plan, list open questions for counsel instead of legal conclusions.
- Never tell the user their app is compliant or non-compliant.
