# Privacy, Data Confidentiality and Transparency

## Investigation and Observations

The initial investigation of DoHabit focused on how the application handles user-generated information, particularly habit records and completion history. This involved examining browser storage through Google Chrome Developer Tools, testing data persistence after refreshing the application, inspecting exported data and monitoring network activity during interactions.

The browser storage inspection revealed application assets, version-related keys and settings configurations, but the location of habit records could not be identified. Nevertheless, the records remained available after refreshing, indicating that some form of persistent storage is used.

The export functionality was also examined and found to include habit information, achievements, settings and completion records, represented partly through strings of seemingly random letters and numbers. These may be internal identifiers or encoded values, although their purpose remains unclear. Additionally, no external requests were observed while creating or completing habits. While this suggests that routine data may be handled on the user's device, the exact storage mechanism and overall network behaviour remain unverified.

## Data Confidentiality and User Control

The ability to export habit records, achievements and settings is a positive aspect of DoHabit because it gives users greater control over their information. Habit trackers can accumulate personal behavioural information over time, including daily routines, consistency and personal goals. Users may consider these records private, even if they do not contain conventional sensitive information such as financial or medical details.

The absence of observed external requests during testing provides some reassurance about the application's behaviour under the examined conditions. However, the exact storage mechanism or how the records are protected could not be established. For example, it remains unclear whether the information is stored in browser databases, another browser storage mechanism or a different implementation. 

This uncertainty is important because persistent storage does not automatically guarantee confidentiality. If records are accessible through the browser or device, their privacy may depend partly on how that device and browser are secured. Therefore, further investigation would be necessary before making stronger claims about the application’s data protection practices.

## Transparency and User Awareness

Another concern is the limited information available to users about how their information is handled. During testing, a privacy notice or terms of use within the application could not be found. Although the application provides import and export functionality, these features do not explain where the original records are stored, whether information is transmitted externally under other circumstances or what happens to the data when users clear their browser storage.

This creates a transparency issue as users should not have to rely on technical tools or inspect browser storage to understand how an application manages their personal information. Clear explanations of data storage, collection, retention and transfer would allow users to make more informed decisions about whether they are comfortable using the application.

It is important to distinguish between a lack of transparency and evidence of actual misuse. The investigation did not establish that DoHabit transfers habit records to external servers or misuses user information. Rather, the concern is that its data-handling arrangements are not sufficiently clear from the information gathered. The unverified storage mechanism, encoded export strings and reliance on browser/device security are technical ambiguities rather than proven technical defects, especially since no external leaks or crashes were observed.

## Ethical Evaluation

The core issue is primarily ethical because even if DoHabit's technical implementation turns out to be completely safe and strictly local, omitting a privacy notice and forcing users to inspect browser storage to understand their data still violates informed consent and user autonomy. These observations can be evaluated using the ACM/IEEE-CS Software Engineering Code of Ethics. Clause 3.12 states that software engineers should develop software and related documentation that respects the privacy of those affected by the software. Although DoHabit offers data export and showed no external requests during tested interactions, the lack of clear explanations about its storage arrangements makes it difficult for users to understand how their information is managed. Respecting privacy should not only limit unnecessary data exposure but also provide users with sufficient information about relevant data practices.

Clause 1.03 is also relevant because it concerns approving software only when there is a well-founded belief that it is safe, meets appropriate requirements and does not diminish quality of life or privacy. In this context, insufficient information about data handling makes it more difficult to assess whether the application adequately protects users' privacy. Clearer explanations would help users make informed decisions about recording their personal routines.

From a deontological perspective, developers have a responsibility to respect users as individuals rather than treating their personal information merely as a means of providing or improving a service. This creates an ethical responsibility to communicate relevant data-handling practices, even when providing such information may require additional development effort. By making these practices understandable, developers support user autonomy and allow individuals to decide whether they are comfortable using the application.