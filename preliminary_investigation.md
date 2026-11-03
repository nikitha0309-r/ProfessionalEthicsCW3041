# 2. Preliminary Investigation

The basis of our findings comes from our first-hand explorations of the app: creating habits, completing them, checking streaks and progress charts, writing journal notes, triggering achievements, reopening the application, and inspecting privacy-related features and browser storage. This was an exploratory assessment, not a technical audit. It made clear four issues; each linked to an observed feature.

### Issue 1: Privacy and transparency (no terms of use or privacy notice)
DoHabit’s data appeared to be held in the browser’s local storage, and the application states that no remote servers are used. This can be seen as a positive choice as it avoids potential concerns surrounding the security and privacy of remote storage. However, data can be lost if users clear browsing data, change browser or device, or encounter a storage problem. Users should be told where their information is kept, what could cause its loss, and how to export or delete it. Our concern is not that DoHabit shares data externally, but that its data handling is never explained in the interface.

### Issue 2: Data control and portability (import and export)
Local import and export let users back up or move their records, reducing dependence on a single browser. Portability, however, is not the same as control. Kimak et al. (2014) recovered readable IndexedDB data after deletion using forensic tools and local filesystem access. This raises a potential concern for personal habits and journal notes, including exported backups. We have not established whether DoHabit encrypts these records, whether deleted records remain recoverable, or whether exports restore reliably. These are questions for Part 2, not confirmed vulnerabilities in DoHabit.

### Issue 3: Behavioural influence (streaks, achievements and reward pop-ups)
These features make progress visible and encourage users to stay consistent with habit tracking. The pop-ups appeared to follow standard triggers, although we did not test every trigger. Gamified rewards may motivate some users while discouraging others who miss a day or lose a streak. We did not observe harm; it is a potential risk that follows from the design.

### Issue 4: Usability and accessibility (system-based appearance modes, limited features)
DoHabit follows system light and dark preferences, which spares users from changing its appearance manually. This alone, however, does not show that the application is accessible to people with visual, motor or other needs. While a limited presence of accessibility features is not necessarily unethical for a narrow-purpose app, a question is raised of whether the interface communicates its capabilities clearly and supports intended users.