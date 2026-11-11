# Product Backlog

## Team Information

- Team name: Terminal 3  
- Project title: Pasada  
- Primary user group for the first release: Daily commuters and out-of-town visitors  
- Format: User stories with one use case&nbsp;

| Member | GitHub username | Personal CSC181 repository |
| :---- | :---- | :---- |
| Steve Nash H. Llamedo&nbsp; | stebbn&nbsp; | https\://github.com/stebbn/CSC181/ |
| Rey Mark E. Degamo | Mark\_Degams | https\://github.com/Mark-Degams/csc181 |
| Brent Jehu Senica&nbsp; | HiraethAKR&nbsp; | https\://github.com/HiraethAKR/CSC181/ |
| Joexua Ross Rieck L. Paco | rpaco06 | https\://github.com/rpaco06/CSC181/ |

<!-- Add rows for all members. -->

&nbsp;

## 1\. Interview Summary

| Code | Stakeholder role | Date | Method | Interviewer(s) |
| :---- | :---- | :---- | :---- | :---- |
| \[V1\] | Primary User (Out-of-Town Visitor)&nbsp; | 2026-10-23&nbsp; | Online via Messenger&nbsp; | Steve Nash H. Llamedo&nbsp; |
| \[V2\] | Primary User (Senior Citizen)&nbsp; | 2026-10-23&nbsp; | Informal in-person interview | Rey Mark Degamo&nbsp; |
| \[V3\] | Primary User (Out-of-Town Visitor)&nbsp;&nbsp; | 2026-11-11 | Informal in-person interview | Brent Jehu Senica |
| \[V4\] | Primary User (Student Boarder) | 2026-11-11 | Informal in-person interview | Joexua Ross Rieck Paco |

&nbsp;

## 2\. From Interview Notes to Needs

| ID | Source | What we heard or saw | Underlying need | Requirement idea | Type |
| :---- | :---- | :---- | :---- | :---- | :---- |
| F1 | V1 | Uses Google Maps and asks locals for directions. | Reliable route mapping without requiring local knowledge. | Digital route mapping system. | F |
| F2 | V1 | Confused Petron for Shell and got dropped off kilometers away. | Clear, unambiguous stop identification. | Visual landmark tags for specific drop-off points. | F |
| F3 | V1 | Hands over standard minimum fare or relies on asking the driver. | Certainty regarding exact travel costs before riding. | Automated fare calculator based on travel distance. | F |
| F4 | V1 | Reads moving jeepney signboards to guess where to transfer. | Clear instructions on connecting routes. | Explicit transfer point guides mapped in the app. | F |
| F5 | V2 | Avoids Miltrasco buses because fares fluctuate compared to jeepneys. | Transparency in pricing differences between vehicle types. | Fare lookup separated by operator/vehicle type. | F |
| F6 | V2 | Sits at the back and cannot ask the driver for the senior fare. | Accessible pricing information without interacting with the driver. | Upfront fare display on a mobile screen. | F |
| F7 | V2, V3 | Fare changed from 22 to 23 and back to 22 within weeks (V2). A driver blamed a fare change on fuel prices, and nothing was announced (V3). | Verification that the fare matrix is current and official. | Display a "last updated" timestamp for all fare data. | Q |
| F8 | V2 | Drivers sometimes do not give the senior discount even when asked. | Concrete proof of the official discounted rate. | Show regular and discounted fares side by side. | F |
| F9 | V3 | Told “near the school,” but the barangay had two; went to the wrong one and lost about an hour. | Tell apart places that share a name. More useful for establishments with multiple branches | Landmark tags show place type and nearest cross-street. | F |
| F10 | V3 | Overpaid on tricycle rides in a new area and since then lowballs and waits for the driver to counter. | A reference price before haggling. | Reference fare for jeepney/bus. Tricycle/sikad reference fare deferred (US-11, Won’t-have). | F |
| F11 | V3 | Trusts locals over Google Maps because outdated roads sent him down barely passable routes. | Data that matches local reality. | Let users report outdated data. | F |
| F12 | V3 | Said “Hardest part is not knowing the names of places” and mentioned his son rode the wrong jeepney in week one. | Learn places and stop names before traveling. | Full stop list and landmark names. | F |
| F13 | V3 | Available transport differs by region (jeepneys vs. tricycles/sikads). | Coverage limits are clear. | Pilot limited to Iligan jeepney/bus. | C |
| F14&nbsp; | V4&nbsp; | Pays the regular fare when seated at the back because yelling “student” is awkward&nbsp; | Claim the discount without speaking&nbsp; | High-contrast screen showing the exact fare to show the driver&nbsp; | F&nbsp; |
| F15&nbsp; | V4&nbsp; | Drivers say the student discount doesn’t apply on weekends or breaks, or without an ID&nbsp; | Know the official eligibility rules&nbsp; | Short eligibility note next to the discounted fare&nbsp; | F&nbsp; |
| F16&nbsp; | V4&nbsp; | Guesses the fare and gets shortchanged on a ₱20 coin&nbsp; | Exact coin and change breakdown&nbsp; | Fare view shows amount to pay and change due&nbsp; | F&nbsp; |
| F17&nbsp; | V4&nbsp; | Wants picture-based landmarks for MSU-IIT, Tibanga, San Miguel&nbsp; | Recognize drop-offs by sight&nbsp; | Photo tags on main student drop-offs&nbsp; | F&nbsp; |

## 3.a Assumption Log

| ID | Assumption | Risk if wrong (High/Medium/Low) | How we will check it |
| :---- | :---- | :---- | :---- |
| A1 | Fluctuating fares (like the 22 to 23 jump, and unannounced fare change) are due to driver discretion/error rather than official LTFRB daily matrix changes. | High | We will cross-reference reported fare variations with the official LTFRB Iligan matrix. |
| A2 | Commuters have mobile internet access while in transit to actively check the app. Others also say that signal is a non-issue when using specific functionalities on certain applications. | Medium | We will evaluate if users need an offline caching feature for routes during our next testing phase. |
| A3 | Visitors will act on the app’s landmark and fare information without first confirming it with a local, even when a local says otherwise.&nbsp; | High | Scenario-based test with 5 unfamiliar users, including a task where a “local” contradicts the app. Judge with the amount of unfamiliar users trusting the app more than the “local”. Also ask the trust question in upcoming interviews.&nbsp; |
| A4&nbsp; | The student discount applies on weekends and school breaks&nbsp; | High&nbsp; | Read RA 11314 and ask LTFRB or the city transport office. Don’t put eligibility text in the app until this is confirmed.&nbsp; |

&nbsp;

## 3.b User Stories

| ID | User story | Source finding(s) | Epic | INVEST check |
| :---- | :---- | :---- | :---- | :---- |
| US-01 | As an out-of-town visitor, I want to see a suggested transit route based on my origin and destination, so that I don't get lost. | F1 | Routing | Yes |
| US-02 | As a commuter, I want to see distinct visual landmarks for my drop-off point, so that I don't get off at the wrong place. | F2, F9, F17 | Routing | Yes |
| US-03 | As a new resident, I want to see explicit transfer points, so that I don't have to guess by reading moving jeepney signboards. | F4 | Routing | Yes |
| US-04 | As a passenger, I want to calculate my exact regular fare before boarding, so that I don't overpay. | F3, F6, F10 | Fares | Yes |
| US-05 | As a senior citizen, I want to see my discounted fare side-by-side with the regular fare, so that I know what to prepare. | F8 | Fares | Yes |
| US-06 | As a careful commuter, I want to compare fares across different operators (e.g., bus vs. jeepney), so that I can choose the cheapest ride. | F5 | Fares | Yes |
| US-07 | As a commuter, I want to see the "last updated" date on the fare matrix, so that I know if the price is current. | F7 | Fares | Yes |
| US-08 | As a user with poor eyesight, I want the app to display fares in a large, simple font, so that I can read it without my glasses. | F6 | UI/UX | Yes |
| US-09 | As an observant commuter, I want to report an outdated route or fare, so that the static data can be corrected for everyone. | F7, F11 | Maintenance | Yes |
| US-10 | As a commuter, I want to browse a route’s complete list of stops, so that I can see everywhere it passes before deciding to ride. | F1, F2, F12 | Routing | Yes |
| US-11 | As an out-of-town visitor, I want a reference fare for tricycle and sikad rides, so that I can negotiate fairly. | F10, F13 | Fares | Yes |
| US-12&nbsp; | As a student boarder, I want a high-contrast screen showing my exact discounted fare and change, so that I can show the driver without announcing it across a crowded jeepney.&nbsp; | F14, F16 | Fares | Yes |
| US-13 | As a student, I want to see when the student discount applies, so that I can answer a driver who says it doesn’t.&nbsp; | F15&nbsp; | Fares | Yes |

&nbsp;

### Epics and how we split them

| Epic | Split into | How we split it |
| :---- | :---- | :---- |
| Fares | US-04, US-05, US-06, US-07, US-11, US-12, US-13 | By data type and user role (splitting basic regular fares from conditional discounts and operator-specific rates to keep stories small). |

Stories we rewrote

1. Before: As a user, I want to see the route and fare so I can travel safely. After: Split into US-01 (Routing) and US-04 (Fares). Reason: The original story was too large and lacked the Independent and Small qualities (INVEST); routing and fare calculation are distinct technical challenges.  
2. Before: As a user, I want large text so I can read the app. After: US-08 (As a user with poor eyesight, I want the app to display fares in a large, simple font...). Reason: The original lacked a specific role and clear value (missing Specificity).

## 4\. Acceptance Criteria

### US-01: Calculate transit route

Acceptance criteria:

- [x] The system returns at least one valid jeepney or bus route based on selected origin and destination.  
- [x] The route polyline is visibly rendered on the map interface.  
- [x] (unhappy) The system displays "No route found" if the destination is outside the pilot coverage area.

Scenario 1: Normal route calculation

```gherkin
Given the user selects "MSU-IIT" as origin and "City Public Plaza" as destination
When the user taps "Find Route"
Then the system displays the "Tibanga-City Proper" jeepney route on the map
```

&nbsp;

Scenario 2: Unreachable destination (Unhappy path)

```gherkin
Given the user selects an origin within coverage and a destination outside Iligan City limits
When the user taps "Find Route"
Then the system displays an "Out of coverage area" error message
```

&nbsp;

### US-02: Visual landmark tags

Acceptance criteria:

- [x] Stop locations are marked with distinct icons on the map.  
- [x] Tapping a stop icon displays the specific landmark name (e.g., "Petron Station").  
- [x] Landmarks sharing the same name have an extended name that includes the branch or street.  
- [x] (unhappy) If the drop-off has no distinct landmark, the system displays the nearest cross-street intersection.

Scenario 1: Same-name places&nbsp;

```gherkin
Given an area with 2 branches of the same franchise
When the user taps either stop icon 
Then the system displays "[Franchise]:[Branch]" with the nearest cross-street` 
```

&nbsp;

Scenario 2: No distinct landmark (Unhappy path)&nbsp;

```gherkin
`Given a drop-off point with no named landmark 
When the user taps the stop icon 
Then the system displays the nearest cross-street intersection` 
```

### US-03: Explicit transfer points

Acceptance criteria:

- [x] Multi-leg journeys highlight transfer points with a unique "Transfer" node.  
- [x] Step-by-step text directions state exactly which route to board next.  
- [x] (unhappy) If a transfer requires walking more than 500 meters, the system displays a "Long walk required" warning.

Scenario 1: Required transfer

```gherkin
Given a trip that requires two different jeepney routes
When the route is generated
Then the exact intersection where the user must alight and wait for the second jeepney is highlighted
```

&nbsp;

Scenario 2: Excessive transfer distance (Unhappy path)

```gherkin
Given a calculated route transfer where the next stop is 600 meters away
When the route instructions are displayed
Then a warning badge indicating "Long walk required" is shown next to the transfer step
```

&nbsp;

### US-04: Calculate exact regular fare

Acceptance criteria:

- [x] The calculated fare automatically displays upon successful route generation.  
- [x] The fare matches the official LTFRB distance-based matrix for the selected route.  
- [x] (unhappy) If route distance data is missing, the system displays "Fare calculation unavailable."

Scenario 1: Standard fare calculation

```gherkin
Given a successful route spanning 5 kilometers
When the route details load
Then the system displays the exact base fare plus per-kilometer add-ons
```

&nbsp;

Scenario 2: Missing distance data (Unhappy path)

```gherkin
Given a route where the total distance segment is undefined in the dataset
When the system attempts to calculate the cost
Then the UI displays "Fare calculation unavailable" instead of a wrong amount
```

&nbsp;

### US-05: Side-by-side discounted fare

Acceptance criteria:

- [x] A toggle or list view clearly labels "Regular" and "Discounted (Student/Senior/PWD)" prices.  
- [x] The discounted price accurately reflects the mandated 20% reduction.  
- [x] (unhappy) If the selected vehicle type does not legally require a discount, the system disables the discount view and shows a tooltip explanation.

Scenario 1: Viewing discount

```gherkin
Given the fare details screen is open for a valid jeepney route
When the user looks at the pricing section
Then both the "Regular: ₱13.00" and "Discounted: ₱10.40" amounts are displayed side-by-side
```

&nbsp;

Scenario 2: Ineligible discount (Unhappy path)

```gherkin
Given a route utilizing a private shuttle that is exempt from mandated discounts
When the user views the fare section
Then the discounted fare is hidden and a "No discount applicable" tag is shown
```

### US-06: Compare fares across operators

Acceptance criteria:

- [x] Alternative vehicle modes (e.g., bus vs. jeepney) are shown if they service the same route.  
- [x] Fares for both operators are listed adjacent to each other for easy comparison.  
- [x] (unhappy) If only one operator services the route, the comparison UI is hidden.

### US-07: Fare "last updated" timestamp

Acceptance criteria:

- [x] The fare matrix screen includes a timestamp indicating the latest data revision.  
- [x] The date format is clear and localized (e.g., "Updated: Oct 2026").  
- [x] (unhappy) If the timestamp cannot be retrieved, display "Update date unknown."

### US-08: Large text interface for fares

Acceptance criteria:

- [x] The fare amount is displayed using a minimum font size of 24sp (scale-independent pixels).  
- [x] High contrast colors (e.g., black on white) are used for the pricing block.  
- [x] (unhappy) If the user's device system font is scaled to maximum, the app's layout wraps text cleanly without cutting off the fare.

### US-09: Report outdated static data

Acceptance criteria:

- [x] A "Report Error" button is visible on every route and fare detail screen.  
- [x] The user can select between "Wrong Route", "Wrong Fare", “Outdated route/landmark” in a dropdown.  
- [x] (unhappy) If the user attempts to submit a blank report, the system blocks submission and prompts for details.

### US-10: Browse full list of stops

Acceptance criteria:

- [x] The route details screen features an expandable "View all stops" list.  
- [x] Stops are listed in chronological order from origin to destination.  
- [x] (unhappy) If the route has no formally defined stops (only terminal-to-terminal), the list displays "Express route \- no intermediate stops."

### US-11: Reference fare for tricycle and sikad

Acceptance criteria:

- [x] The system displays a reference fare in pesos for a tricycle or sikad ride between an origin and destination inside the pilot coverage area.  
- [x] Each reference fare shows its data source and the date it was last verified.  
- [x] The reference fare carries the label "Reference only. Drivers may quote a different price."  
- [x] (unhappy) If no verified fare data exists for the selected area, the system displays "No reference fare available for this area" and shows no estimated amount.

### US-12: Show-driver fare screen&nbsp;

&nbsp;Acceptance criteria:

- [x] A “Show driver” button appears on the fare details screen of every route that has fare data.  
- [x] Tapping it opens a full-screen view showing the selected fare (Regular or Student/Senior/PWD) in black text on a white background at a minimum of 24px (1.5rem).  
- [x] The user can enter the coin or bill they will hand over, and the screen displays the change due.  
- [x] (unhappy) If the route has no fare data, the screen displays “Fare unavailable” and shows no amount.  
- [x] (unhappy) If the entered amount is lower than the fare, the screen displays “Amount is less than the fare” and shows no change figure.

### US-13: Discount eligibility note

Acceptance criteria:

- [x] A “When does this apply?” link appears next to the discounted fare.  
- [x] Tapping it displays who qualifies, which ID is required, and whether the discount applies on weekends and school breaks, together with the source name and the date the rule was verified.  
- [x] The note closes when the user taps “Close” or taps outside it.  
- [x] (unhappy) If the rule has not been verified, the note displays “Not yet confirmed” and shows no rule text

&nbsp;

## 5\. Quality Requirements and Constraints (EARS)

| ID | Requirement | EARS pattern | Type | Source | Number agreed with |
| :---- | :---- | :---- | :---- | :---- | :---- |
| NFR-01 | While the device is offline, the system shall display the last cached static route map and fare matrix. | State-driven | Quality | F1, F3 | 4 |
| NFR-02 | When a user views the fare matrix screen, the system shall display the date the fare data was last verified. | Event-driven | Quality | F7 | 4 |
| NFR-03 | The system shall calculate jeepney and bus fares strictly using the official LTFRB distance-based matrix.&nbsp; | Ubiquitous | Constraint | F3, F5 | 4 |

&nbsp;

## 6\. Use Case

### Use-case diagram

![alt text](<backlog-images/Case Diagram.png>)

### UC-01: Calculate Trip Route and Fare

| Field | Description |
| :---- | :---- |
| Primary actor | Commuter |
| Precondition | The app is successfully loaded with the static route and fare dataset. |
| Main success scenario | 1\. Commuter enters origin and destination landmarks.  2\. System calculates a valid jeepney/bus route.3\. System calculates regular and discounted fares for the distance. 4\. System displays the route map, transfer points, and side-by-side fares. 5\. Commuter selects the route to review visual landmark tags. |
| Extensions | 2a. No direct route found: System calculates a multi-leg route and highlights transfer points. 2b. Destination outside pilot coverage: System displays an "Out of coverage area" error. |
| Postcondition | The commuter knows the exact route, transfer intersections, and fare to prepare. |
| Stories covered | US-01, US-02, US-03, US-04, US-05 |

&nbsp;

## 7\. Story Map

|  | Define Journey | View Route & Transfers | Check Pricing | Trip Detail & Feedback |
| :---- | :---- | :---- | :---- | :---- |
| **Release 1 (MVP)** | US-01 | US-03, US-02 | US-04, US-05 |  |
| **Release 2** |  | US-10 | US-06, US-12, US-13 |  |
| **Later** |  |  | US-07, US-11 | US-08, US-09 |

&nbsp;

## 8\. The Ordered Backlog

| Rank | Story | MoSCoW | Size (S/M/L) | Value / effort quadrant | Sprint |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | US-01 Calculate transit route | Must | M | Big bet | Sprint 1 |
| 2 | US-04 Calculate exact regular fare | Must | M | Big bet | Sprint 1 |
| 3 | US-05 Side-by-side discounted fare | Must | S | Quick win | Sprint 1 |
| 4 | US-03 Explicit transfer points | Must | M | Big bet | Sprint 2 |
| 5 | US-02 Visual landmark tags | Must | M | Big bet | Sprint 2 |
| 6 | US-06 Compare fares across operators | Should | S | Quick win | Later&nbsp; |
| 7 | US-10 Browse full list of stops | Should | S | Quick win | Later&nbsp;&nbsp; |
| 8 | US-12 Show-driver fare screen&nbsp; | Should&nbsp; | M | Big bet&nbsp; | Later |
| 9 | US-08 Large text interface&nbsp; | Should&nbsp; | S | Fill-in | Later |
| 10 | US-07 Last updated&nbsp; | Could | S | Fill-in | Later |
| 11 | US-13 Discount eligibility note&nbsp; | Could | S | Quick win&nbsp; | Later&nbsp; |
| 12 | US-09 Report outdated data&nbsp; | Could&nbsp; | S&nbsp; | Quick win&nbsp; | Later&nbsp; |
| 13 | US-11 Tricycle/sikad fare&nbsp; | Won’t | M&nbsp; | Money pit | Out of Scope |

&nbsp;

### How we ordered it

US-01 is first because every other story depends on a route being found, and V1's first problem was not knowing which vehicle to take (F1). US-04 and US-05 come next because both interviews showed fare uncertainty (F3, F6, F8), and US-05 is small. US-03 and US-02 follow because they depend on the route data from US-01 and address V1's and V3’s transfer and wrong-drop-off problems (F4, F2, F9). The main risk is the fare and route data, so Sprint 1 builds the dataset for a small set of pilot routes and records the source of each fare. The Release 2 and Later stories (US-06, US-10, US-07, US-09, US-08, US-12, US-13) improve the core path but are not needed to complete it. US-11 is a Won't-have for the first release. Only V3 raised tricycle and sikad fares (F10), no official fare source has been confirmed (A1), and the pilot is limited to jeepney and bus routes (F13). US-12 and US-13 come from V4 (F14, F15, F16). US-12 builds on the fare stories, and US-13 waits for verification of the student discount rules (A4).&nbsp;

### Capacity check

| Question | Answer |
| :---- | :---- |
| How many Must-have stories, and their total size? | 5 Must-have stories: 4 M and 1 S. |
| Do the Must-haves fit in about 60% of our time for two sprints? | Yes. There are only 5 Must-haves (4 M, 1 S), and the data is limited to a small set of pilot routes.&nbsp; |
| Do the Release 1 stories form one complete path through the core workflow? | Yes |
| Are all L-sized Must-have stories split? | Yes |

&nbsp;

## 9\. Definition of Done

- [ ] Every acceptance criterion for the story, including its unhappy path, passes when run on a device or emulator by a team member who did not write the code.  
- [ ] For Must-have stories, every Given–When–Then scenario has been run and its result recorded.  
- [ ] At least one other team member reviewed the code, and it is merged to the main branch through a pull request.  
- [ ] Any route or fare data the story uses has its source and revision date recorded in the dataset.  
- [ ] The story was shown working at the sprint review, with no open defects against its acceptance criteria.

## 10\. Traceability Table

| Story | Problem or goal it addresses | Source finding(s) | Test cases (Week 9\) |
| :---- | :---- | :---- | :---- |
| US-01 | Know which jeepney or bus to take without local knowledge | F1 | \[Leave blank for now\] |
| US-02 | Avoid getting off at the wrong stop | F2, F9, F17 | \[Leave blank for now\] |
| US-03 | Know where to transfer without reading signboards | F4 | \[Leave blank for now\] |
| US-04 | Know the exact fare before boarding | F3, F6, F10 | \[Leave blank for now\] |
| US-05 | Verify the correct discounted fare | F8 | \[Leave blank for now\] |

&nbsp;

Gaps found:&nbsp;

- US-08 has no supporting finding. It cites F6, which is about a senior who cannot ask the driver for the fare, not about eyesight. Action: keep it as Could, mark the source as unverified, and ask about readability in the next interview round.  
- F10 (tricycle and sikad fares) is covered by US-11, a Won't-have for the first release. Action: kept in the backlog at rank 13 and revisited once the fare source in A1 is confirmed.&nbsp;&nbsp;  
- F13 (transport differs by region) is a constraint with no story of its own. Action: covered by the pilot-coverage unhappy path in US-01 and by limiting the pilot to Iligan jeepney and bus routes.&nbsp;

## 11\. Validation

### Team review

| Problem found | Story or requirement | How we fixed it |
| :---- | :---- | :---- |
| Must-have story had no Given–When–Then scenarios, but the checklist requires at least 2 per Must-have.&nbsp; | US-02&nbsp; | Added a same-name landmark scenario and a no-distinct-landmark unhappy-path scenario.&nbsp; |
| Story map placed US-02 in Release 2, but the backlog ranks it Must in Sprint 2, so Release 1 was incomplete.&nbsp; | US-02, Section 7&nbsp; | Moved US-02 into Release 1 so the Release 1 line crosses all four journey steps.&nbsp; |
| The senior citizen interview is coded V2 in Section 1 but S1 in Section 2, so findings F5–F8 cannot be traced to an interview.&nbsp; | F5–F8, Section 1&nbsp; | Standardized on one code across both sections.&nbsp; |
| Story cites a finding that does not support it (F6 is about asking the driver, not eyesight).&nbsp; | US-08&nbsp; | Flagged the missing source under "Gaps found" and marked it for verification.&nbsp; |

&nbsp;

### Stakeholder walk-through

| Stakeholder | Date | What they said | What we changed |
| :---- | :---- | :---- | :---- |
| V1 (Out-of-Town Visitor)&nbsp; | 2026-11-11 | Upfront routes and transfer points solve her struggle of guessing where to switch jeeps. Street names confuse her because locals use landmark names (Shell vs. Petron). Seeing the fare beforehand removes the stress of asking drivers.&nbsp; | Kept US-01 and US-04 in Release 1\. Added brand-name examples (gas stations, bakeries) to the US-02 criteria.&nbsp; |
| V2 (Senior Citizen)&nbsp; | 2026-11-11 | Liked seeing regular and senior fares side by side. Numbers need a very large font to read on a bumpy ride. Per-operator prices matter because bus and jeepney rates differ.&nbsp; | No change to US-05, already in Sprint 1\. Raised US-08 from Could to Should and cited this comment as its source. US-06 unchanged.&nbsp; |
| V3 (Out-of-Town Visitor) | 2026-11-11 | Same-name landmarks (two schools in one barangay) cause delays if the app isn’t specific. Map apps can send users down impassable roads, so flagging wrong data is needed. A reference fare helps against overcharging.&nbsp; | No change. US-02 already requires cross-streets and facility types, US-09 already covers reporting, and US-04 covers the reference fare.&nbsp; |
| V4 (Student Boarder)&nbsp; | 2026-11-11 | Release 1 routing and fares are enough for a first independent trip. Photo landmarks shouldn’t be delayed. He’d trust a driver over the app unless the app shows its data is official. The “Show driver” screen saves him from shouting “student.”&nbsp; | Moved US-02 into Release 1 and updated the story map. Added a source and last-updated line to the fare screen (not an “official” claim until A1 is verified). Updated A3.&nbsp; |

&nbsp;

## 12\. Open Questions for Sprint 1

1. Where will we get the official fare matrix per operator and the route list for the pilot routes, and which routes will the pilot cover?  
2. How will we collect and verify landmark names for each pilot stop, for example telling the Shell and Petron stations near Mahayahay apart?  
3. How do we confirm whether fare changes are official or driver error (LTFRB/city transport office)?  
4. How do we handle landmark names that repeat in the same barangay?  
5. Does the student discount apply on weekends and school breaks, and what ID is required?&nbsp;  
6. What rounding rule applies to the 20% discounted fare?&nbsp;

## 13\. Member Contribution Record

\[Record actual contributions, including interviews, analysis, writing stories and criteria, and reviewing.\]

| Member | Interviews or analysis | Stories, criteria, or use case | Review or validation |
| :---- | :---- | :---- | :---- |
| Steve Nash H. Llamedo | V1 Interview, Defined problem areas for out of town visitors | Core routing stories: US \- (01 \-04), Use Case | Idea checked, Formatting |
| Rey Mark E. Degamo | V2 Interview, Section 8 | F5-F8, US- (05-08) | Interview relation check&nbsp; |
| Brent Jehu Senica | V3 Interview, Sections 10 & 11\.&nbsp; | F9-F13, US-02, US \- 11 | Sections 4, 5, 6, 7, 8, 9, & 12\. Also  Fact checked, proofread, and Source checked. |
| Joexua Ross Rieck L. Paco | V4 Interview, Stakeholder walk-through & Section 12 | F14-F17, US-12, US-13 | Reviewed the backlog, flagged inconsistencies&nbsp; |

&nbsp;

## 14\. References

\- CSC181 Week 4 lecture slides

\- Wake, B. (2003). "INVEST in Good Stories, and SMART Tasks." XP123.

\- Mavin, A., Wilkinson, P., Harwood, A., and Novak, M. (2009). "Easy Approach to Requirements Syntax (EARS)." IEEE International Requirements Engineering Conference.

\- Team interview notes V1, V2, V3, V4 (primary data).

## 15\. Team AI Use Declaration

Select one option:

- [ ] No generative AI tools were used by any member in preparing this submission.  
- [x] One or more members used generative AI tools. Details are provided below.

\[If AI was used, complete the table. If not, write Not applicable.\]

| Member who used AI | Tool | Purpose and sections assisted | How output was checked or revised |
| :---- | :---- | :---- | :---- |
| Brent Jehu Senica | Google Gemini | Interview log | Reread everything to make sure the translated piece was faithful to what was said in the original audio log |

### Main prompts or interaction summary:

- \[Pasted Audio transcript\] Translate the following transcript to english

We acknowledge that AI-generated suggestions are not evidence of actual stakeholder interviews, feedback, or verified user needs. Every finding in Section 2 and every walk-through in Section 11 comes from a real person we spoke to or observed. We remain responsible for the accuracy and explainability of this submission.

## 16\. Team Confirmation

We confirm that this document reflects our team's agreed-upon product backlog. All members listed below reviewed the final version, and each member will upload the same Markdown file to their personal CSC181 repository.

| Member | Reviewed final version |
| :---- | :---- |
| Steve Nash H. Llamedo | Yes |
| Rey Mark E. Degamo | Yes |
| Brent Jehu Senica | Yes |
| Joexua Ross Rieck L. Paco | Yes |

&nbsp;

## Submission Checklist

- [x] Interviews cover at least two stakeholder groups, with sources coded and no personal information.  
- [x] The needs table has at least 8 findings, each labelled F, Q, or C.  
- [x] Assumptions are recorded separately from evidence.  
- [x] There are 10 to 15 user stories, each with a real role, a "so that", and at least one finding.  
- [x] Epics are split, and at least two rewrites are recorded.  
- [x] Every story has at least 3 acceptance criteria, including an unhappy path, with no weak words.  
- [x] Every Must-have story has at least 2 Given–When–Then scenarios.  
- [x] At least 3 quality requirements or constraints use EARS patterns.  
- [x] One use case has a diagram, a main success scenario, and at least 2 extensions.  
- [x] The story map has a Release 1 line that crosses every journey step.  
- [x] Every story has a MoSCoW label and a size, and the backlog is in one order with no ties.  
- [x] Must-haves fit in about 60% of capacity. Won't-have stories are kept, not deleted.  
- [x] A Definition of Done is included.  
- [x] The traceability table covers every Must-have story.  
- [x] The team review and the stakeholder walk-through are recorded.  
- [x] Contributions, references, and AI use are declared.  
- [x] All members reviewed the same final document.  
- [x] Each member saved the file as `activities/product-backlog.md`, with images in `activities/backlog-images/`.  
- [x] Each member committed and pushed their copy to their personal repository.  
- [x] Each member submitted their own GitHub file link through MOLE before November 11, 2026 23:59:59.