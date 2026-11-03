Create a literature review md file.

### Self-tracking, privacy and data control (Issues 1 and 2)

Wieczorek et al. (2023) reviewed 65 works on the ethics of self-tracking and found recurring concerns surrounding privacy, surveillance, ownership and control of data, autonomy, design shortcomings, and effects on self-perception, alongside benefits such as empowerment and wellbeing. Sax et al. (2018) examine mobile health apps through consumer law and argue that apps’ design and data practices can undermine user autonomy for commercial ends.

The two sources differ in scope: Wieczorek et al. map ethical themes broadly, while Sax et al. focus on commercial exploitation. Both, however, assume data flows to companies or third parties. DoHabit’s local storage shifts the risk away from surveillance and towards data loss, ownership, and recoverability, so these findings guide what to look for but cannot be applied directly.

Kimak et al. (2014) used forensic tools to recover deleted, unencrypted IndexedDB data. Their findings motivate testing DoHabit’s data protection and deletion, but the outdated test environment limits their applicability to current browsers.

## Transparency and dark patterns (Issues 1 and 3)

Huckvale et al. (2019) found that only 25 of 36 top-ranked health apps had a privacy policy, and many did not disclose third-party data sharing. DoHabit appears to keep data local, but repeats their failure to explain data handling to users. Huckvale et al. checked app behaviour through network traffic rather than stated policy, a method we adopt for Part 2.

Gray et al. (2018) classify manipulative interface designs into five types: nagging, obstruction, sneaking, interface interference and forced action. Mathur et al. (2019) found such patterns widespread across thousands of shopping websites.

Both studies concern persuasion towards purchases, not habit tracking, and a missing privacy notice is not itself a dark pattern - its relevance is as a checklist: in Part 2 we can test whether DoHabit’s reward pop-ups nag or pressure users.
