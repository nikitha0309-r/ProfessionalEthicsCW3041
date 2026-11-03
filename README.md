# An Ethical Evaluation of DoHabit Using the ACM/IEEE-CS Software Engineering Code of Ethics: A Preliminary Proposal

---

## Group Members

| S.No. | Name | Student ID |
|:---:|---|:---:|
| 1 | Shawn Chan | 20590530 |
| 2 | Ivan Khomiakov | 20613314 |
| 3 | Jeremy Mwakio Kilei | 20579147 |
| 4 | Nikitha Rajagopalan | 20595637 |
| 5 | Christopher Wood | 20683271 |

---

## Table of Contents

1. [Introduction and System Selection](#1-introduction-and-system-selection)
2. [Preliminary Investigation](#2-preliminary-investigation)
3. [Literature Review](#3-literature-review)
4. [Ethical Framework Proposal](#4-ethical-framework-proposal)
   - [4.1 Software Engineering Code Clauses](#41-software-engineering-code-clauses)
   - [4.2 Ethical Theories](#42-ethical-theories)
   - [4.3 Where the Code Is Insufficient](#43-where-the-code-is-insufficient)
5. [Plan for Part 2 and Conclusion](#5-plan-for-part-2-and-conclusion)
6. [References](#references)

---

# 1. Introduction and System Selection

Habit-tracking applications help users build routines by recording activity and displaying progress. Features such as streaks, achievements and rewards can encourage consistency, but raise ethical questions about privacy, transparency, autonomy and responsible design. This proposal examines DoHabit, a web-based habit tracker that lets users create habits, log progress, keep journal notes and earn achievements.

Being a small, unresearched application with a strong influence on users’ daily lives, we found DoHabit to be an ideal subject for an ethical review. The app contains various ethically debatable features such as the storage of personal habit and journal data and the use of streaks and reward pop-ups to shape everyday behaviour. Additionally, DoHabit’s scope is limited which will allow us to explore features directly rather than relying on stated purpose or potentially inaccurate guesswork.

One immediate issue we noticed was an absence of terms of use or a privacy notice. While the app’s apparent local-only storage suggests low privacy risk, users cannot confirm the confidentiality of their data.

This proposal reports our preliminary findings, reviews related literature by theme, and sets out a framework combining the ACM/IEEE-CS Software Engineering Code of Ethics and Professional Practice (the Code) with two ethical theories (Utilitarianism and Deontology). It ends with a plan for Part 2.

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

# 3. Literature Review

Little or no research addresses DoHabit specifically, so we draw on the wider categories it belongs to. We organise the literature by theme and link each theme to our issues.

### Self-tracking, privacy and data control (Issues 1 and 2)

Wieczorek et al. (2023) reviewed 65 works on the ethics of self-tracking and found recurring concerns surrounding privacy, surveillance, ownership and control of data, autonomy, design shortcomings and effects on self-perception, alongside benefits such as empowerment and wellbeing. Sax et al. (2018) examine mobile health apps through consumer law and argue that apps’ design and data practices can undermine user autonomy for commercial ends.

The two sources differ in scope: Wieczorek et al. map ethical themes broadly, while Sax et al. focus on commercial exploitation. Both, however, assume data flows to companies or third parties. DoHabit’s local storage shifts the risk away from surveillance and towards data loss, ownership and recoverability, so these findings guide what to look for but cannot be applied directly.

Kimak et al. (2014) used forensic tools to recover deleted, unencrypted IndexedDB data. Their findings motivate testing DoHabit’s data protection and deletion, but the outdated test environment limits their applicability to current browsers.

### Transparency and dark patterns (Issue 1)

Gray et al. (2018) classify manipulative interface designs into five types: nagging, obstruction, sneaking, interface interference and forced action. Mathur et al. (2019) found such patterns widespread across thousands of shopping websites.

Both studies concern persuasion towards purchases, not habit tracking, and a missing privacy notice is not itself a dark pattern - their relevance is as a checklist: in Part 2 we can test whether DoHabit’s reward pop-ups nag or pressure users.

### Behaviour influence and rewards (Issue 3)

Zhu et al. (2024) reviewed 41 articles on digital habit-formation interventions and identified techniques including self-monitoring, goal setting, prompts, cues and virtual rewards, which correspond closely to DoHabit’s streaks and achievements.

Lally et al. (2010) studied habit formation in real life and found that the time to form a habit varied widely and that missing a single opportunity did not materially affect the process. This sits uneasily with streak mechanics, which treat a missed day as a loss.

Together with Wieczorek et al.’s warnings about self-perception, these sources suggest that rewards may support users’ goals but could also create unnecessary pressure. None shows how DoHabit affects its real users, so we treat this as a design risk, not an established harm.

### Accessibility (Issue 4)

We found no research on accessibility in small local apps. The Web Content Accessibility Guidelines 2.2 (W3C, 2023) organise requirements under four principles (perceivable, operable, understandable and robust) and provide testable criteria for keyboard operation, focus visibility and contrast, so we use them as our benchmark.

# 4. Ethical Framework Proposal

## 4.1 Software Engineering Code Clauses

| Issue | Clauses | Why They Apply |
|---|---|---|
| 1. Privacy and transparency | 3.12, 1.03 | Clause 3.12 requires software and related documents to respect privacy, so a missing notice engages it even with local storage. Clause 1.03 requires that software not diminish privacy or quality of life. Local storage is a strength but is not automatically secure. |
| 2. Data control | 3.13, 3.14 | Clause 3.13 covers authorised use of data and 3.14 covers data integrity: exports must preserve records accurately, and users must understand how data can be lost. Neither creates a right to portability or deletion, so the Code only partly covers this issue. |
| 3. Behavioural influence | 4.01, 1.02 | Clause 4.01 requires technical judgements to support human values; clause 1.02 requires engineer, client and user interests to be moderated with the public good. |
| 4. Accessibility | 1.07, 3.10 | Clause 1.07 requires consideration of disabilities and other barriers to access; clause 3.10 requires adequate testing and review. Accessibility is therefore a testing duty, not only a design preference. |

These clauses point to modest improvements: a short notice explaining local storage, data-loss risk and export and deletion options; customisable rewards and flexibility around missed days; and accessibility testing. They are based on perceived potential risks, not evidence of current harm.

## 4.2 Ethical Theories

For ethical discussion, we propose two theories with each highlighting different perceived issues.

### Utilitarianism (Mill, 1863)

Utilitarianism (Mill, 1863) judges actions by their consequences for overall wellbeing. We believe it to be well-suited to discuss Issue 3, which raises the question of whether streaks and rewards are effective enough in helping users to sustain useful routines to outweigh the frustration it may cause for others.

Its weakness is that aggregate benefit can hide harm to a minority, such as users distressed by a lost streak.

### Deontological Ethics (Kant, 1785/1998)

Deontological ethics (Kant, 1785/1998) focuses on duties owed to individuals regardless of outcomes. We believe it to be suited to discuss Issue 1 as it can be argued that users are owed an understanding of how their personal information is handled, regardless of whether it leaves their device.

The use of both of our selected theories in tandem will allow us to test whether our conclusions hold under both outcome-based and duty-based reasoning.

## 4.3 Where the Code Is Insufficient

The Code appears to be insufficient for Issue 3. Clause 4.01 is a broad commitment to human values but does not specify how much motivational pressure is acceptable or when persuasive design becomes manipulation. Clauses 1.02 and 4.01 can also pull apart: one engineer can argue that streaks serve users’ goals while another sees the same feature eroding autonomy.

The decision also lies partly outside the engineer’s control, since retention goals are usually set by product owners. A theory is needed here. Utilitarianism helps weigh motivation against discouragement, while deontology asks whether users are treated as autonomous agents, for example by being able to switch rewards off. The two may disagree, so professional judgement remains necessary.

# 5. Plan for Part 2 and Conclusion

Part 2 will replace assumptions with documented evidence, using repeatable tests that record steps, expected results, actual results and supporting evidence.

### Planned Investigation

1. **Storage and Network Inspection:** We will inspect browser storage and network activity to establish the storage mechanism, any application-level encryption and observed transmissions.

2. **Data Control and Recovery Testing:** We will test import, export, deletion and persistence, including attempting to recover data that is marked as deleted and restoring an export in a clean browser, then comparing restored records with originals.

3. **Behavioural Influence Testing:** We will run the reward system through different completion scenarios, including missed days, and check for dark patterns and user control.

4. **Accessibility Testing:** We will test keyboard navigation, focus visibility, contrast and screen-reader compatibility against WCAG 2.2.

We will also review source code and documentation where available, and classify findings as confirmed defects, missing information, design trade-offs or unresolved questions.

### Conclusion

In conclusion, DoHabit is a simple habit tracker whose most notable concern so far is the absence of a privacy notice or terms of use. Our preliminary evidence does not show data misuse, explicit psychological harm or extensive accessibility failure; it instead points out several areas of potential concern.

The framework gives each issue a Code-based analysis or utilizes an established ethical theory should the Code not be sufficient.

# References

Gray, C. M., Kou, Y., Battles, B., Hoggatt, J., & Toombs, A. L. (2018). The dark (patterns) side of UX design. *Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems*, Article 534. https://doi.org/10.1145/3173574.3174108

IEEE-CS/ACM Joint Task Force on Software Engineering Ethics and Professional Practices. (1999). *Software engineering code of ethics and professional practice* (Version 5.2). IEEE Computer Society. https://www.computer.org/education/code-of-ethics

Kant, I. (1998). *Groundwork of the metaphysics of morals* (M. Gregor, Trans.). Cambridge University Press. (Original work published 1785)

Kimak, S., Ellman, J., & Laing, C. (2014). Some potential issues with the security of HTML5 indexedDB. In *9th IET International Conference on System Safety and Cyber Security (2014)* (pp. 1–6). Institution of Engineering and Technology. https://doi.org/10.1049/cp.2014.0971

Lally, P., van Jaarsveld, C. H. M., Potts, H. W. W., & Wardle, J. (2010). How are habits formed: Modelling habit formation in the real world. *European Journal of Social Psychology, 40*(6), 998–1009. https://doi.org/10.1002/ejsp.674

Mathur, A., Acar, G., Friedman, M. J., Lucherini, E., Mayer, J., Chetty, M., & Narayanan, A. (2019). Dark patterns at scale: Findings from a crawl of 11K shopping websites. *Proceedings of the ACM on Human-Computer Interaction, 3*(CSCW), Article 81. https://doi.org/10.1145/3359183

Mill, J. S. (1863). *Utilitarianism*. Parker, Son, and Bourn.

Sax, M., Helberger, N., & Bol, N. (2018). Health as a means towards profitable ends: mHealth apps, user autonomy, and unfair commercial practices. *Journal of Consumer Policy, 41*(2), 103–134. https://doi.org/10.1007/s10603-018-9374-3

W3C. (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. https://www.w3.org/TR/WCAG22/

Wieczorek, M., O’Brolchain, F., Saghai, Y., & Gordijn, B. (2023). The ethics of self-tracking: A comprehensive review of the literature. *Ethics & Behavior, 33*(4), 239–271. https://doi.org/10.1080/10508422.2022.2082969

Zhu, Y., Long, Y., Wang, H., Lee, K. P., Zhang, L., & Wang, S. J. (2024). Digital behavior change intervention designs for habit formation: Systematic review. *Journal of Medical Internet Research, 26*, e54375. https://doi.org/10.2196/54375

---

*Professional Ethics Coursework – CW3041*
