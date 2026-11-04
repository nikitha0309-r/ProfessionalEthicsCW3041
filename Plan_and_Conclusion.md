# 5. Plan for Part 2 and Conclusion

Part 2 will replace assumptions with documented evidence, using repeatable tests that record steps, expected results, actual results and supporting evidence.

### Planned Investigation

1. **Storage and Network Inspection:** We will inspect browser storage and network activity to establish the storage mechanism, any application-level encryption and observed transmissions.

2. **Data Control and Recovery Testing:** We will test import, export, deletion and persistence, including attempting to recover data that is marked as deleted and restoring an export in a clean browser, then comparing restored records with originals.

3. **Behavioural Influence Testing:** We will run the reward system through different completion scenarios, including missed days, and check for dark patterns and user control.

4. **Accessibility Testing:** We will test keyboard navigation, focus visibility, contrast and screen-reader compatibility against WCAG 2.2.

We will also review source code and documentation where available, and classify findings as confirmed defects, missing information, design trade-offs or unresolved questions.

### Conclusion

In conclusion, DoHabit is a simple habit tracker whose most notable concerns so far are the absence of a privacy notice or terms of use and a lack of accessibility options. Our preliminary evidence also revealed other potential issues surrounding data security and behavioural influence, but these will require more in-depth investigation to confirm or disprove.

With our framework, we analysed and justified each issue, both confirmed and potential, with reference to the Code or fell back to an established ethical theory where the Code was not sufficient.

Our next steps will be to more thoroughly investigate each of our identified concerns to find the extent of their validity, and then to suggest with detailed evidence and full confidence, effective and realistic solutions to these problems.