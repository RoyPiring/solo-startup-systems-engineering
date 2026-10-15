<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up Grok Bot Approval Controls

**Project Link:** [View Project](https://nextwork.ai/projects/ff76331a-6372-4488-98d5-6611bf5dec9b)

**Author:** Roy Piring: Cloud Platform Engineer | Build Master  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_tuwxg57y)

## Establishing a Safe AI Operations Boundary

### Project purpose and safety boundary

I created one Grok Bot helper named Scout for a controlled Day 1 operations lab. Scout could draft content from facts I entered and record only the connections visible on the screen. It could not receive passwords, bank details, real client information, or access to company systems. The work remained under my learning login.

The boundary also kept all external actions under human control. Scout could prepare a message, but it could not send one from this lab. No company app was connected, and the bank connection remained prohibited. This allowed me to test instructions, approval gates, files, and drafting behavior without creating a path into live email, banking, or client tools.

## Preparing Grok Bot for Controlled Work

### Setting up the control environment

I signed in to Grok Bot on the Windows laptop using my learning login. Before creating Scout, I checked the spending, review, and plugin settings that would control its available actions. On-demand spending was set to None, Auto Review was enabled, and no company application appeared in the connected plugin list.

This created a restricted starting environment before the helper received any task. Scout could later work with facts and local lab files, but it had no connection to company mail, banking, or client systems. Confirming these controls first reduced the chance that a default setting or existing connection would silently widen the helper’s reach after creation.

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_y4kxs034)

### Preventing access before Scout begins work

The initial settings prevented Scout from spending beyond the existing plan or carrying out a protected action without review. On-demand spending remained None, so the lab did not authorize extra usage charges. Auto Review remained on, allowing matching actions to pause for my decision instead of proceeding automatically.

The absence of company plugins created the second boundary. Even if Scout drafted operational content, it had no route into live mail, bank, or client applications. This meant I could create the helper without granting access that its Day 1 job did not require. The control environment was established before work began rather than corrected after the helper had already received broader permissions.

## Building Scout's Day 1 Control Set

### Creating Scout and its operating controls

I created the helper with the name Scout and the title Day 1 operations recorder for Pineapple Advisory. Its job was limited to recording only the connections visible in the lab. The connection register showed no connected application, and the bank row remained NEVER, preserving the strongest restriction for financial access.

I also enabled eleven Ask first rules. These rules covered protected actions that had to stop and wait for my review rather than run automatically. No protected action was configured to allow itself. Together, the narrow job, empty connection register, bank prohibition, and approval rules gave Scout a defined working area without granting open operational authority.

### Separating standing rules from approval gates

Scout had four standing rules that described how it should work throughout the lab. Those rules remained attached to the helper and guided every chat. They defined its operating behavior, but they did not replace the separate mechanism that controlled whether a protected action could proceed.

Auto Review served as the approval gate. When an action matched one of the eleven Ask first rules, the gate paused the action and presented it for my decision. This created two distinct controls: Scout’s standing instructions governed how it should behave, while Auto Review determined when it had to stop and request permission before acting.

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_jl0toqdz)

## Proving the Delete Gate and Recording Usage

### Testing a real protected action

I tested the approval boundary with a real deletion attempt against the connection register. The action matched the rule for deleting a file inside /workspace/pineapple/, so Auto Review displayed an approval card before the file could be removed. This tested the gate with an actual protected operation rather than a written example.

After the delete test, I recorded one usage line from the Usage and Billing screen. The entry contained only the plan name and weekly percentage I observed. I did not add an allowance, infer a limit, or create a heading that was not requested. The two actions tested separate controls: protected file handling and accurate recording of visible account information.

### Evidence that the approval gate stopped deletion

The approval card identified the rule covering file deletion inside /workspace/pineapple/. I selected Deny, and Scout did not remove the file. The connection register remained available after the decision, showing that the protected action had stopped before changing the stored record.

The file still contained its purpose line, the bank row marked NEVER, and the row recording None as the connection state. Preserving both rows mattered because the test was intended to verify the gate, not sacrifice the evidence file. The result connected the displayed rule, my denial, and the unchanged file contents in one observable sequence.

### Recording observed plan usage accurately

I opened Usage and Billing and observed Plan: Pro with weekly usage at 1% used. Scout recorded exactly one line in usage.md: 2026-09-15 | Plan: Pro | Weekly usage: 1% used. The entry preserved the date and visible account information without adding interpretation.

Scout did not create a heading, estimate the remaining allowance, or claim a limit that was not shown on the screen. This kept the usage record tied to direct observation. The file served as a small evidence log rather than an account forecast. Its value came from recording only what was visible and refusing to fill missing information with a guess.

## Drafting a Real Message While Keeping Sending Human-Controlled

### Using Scout to prepare a founder-directed draft

I gave Scout the facts needed to prepare one short note for Alex Morgan. The message stated that the draft workshop had moved to Thursday and asked whether Thursday still worked. Scout used only the information I entered and stopped after presenting the draft on the screen.

This task tested whether the helper could produce a useful operational message while remaining inside its Day 1 boundary. The draft had a named recipient, a changed schedule, and one direct question, but it did not require access to a contact list, inbox, or company system. Scout completed the writing task without expanding into delivery.

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_ahq1yedy)

### Maintaining the human send boundary

I did not send the note to Alex Morgan or any other real person. The draft remained on the screen after Scout completed it. Scout did not open an email service, select a recipient, or attempt delivery. No mail application was connected to the helper during the lab.

This preserved the difference between drafting and sending. Scout could help shape wording from approved facts, but I retained responsibility for checking the content, choosing the communication channel, and deciding whether a real message should leave the lab. The lack of a mail connection also supported the rule technically rather than depending only on the helper’s written instruction.

## Verifying the Complete Day 1 Control Set

### Checking the finished controls against the original ask

I reviewed Scout’s identity, title, four standing rules, eleven approval rules, Auto Review setting, plugin list, connection register, and usage file against the original Day 1 requirements. The helper remained named Scout, with the title Day 1 operations recorder for Pineapple Advisory.

The four standing rules were still saved with Scout and remained in force. Auto Review was still enabled, and no company application appeared in the plugin list. Both evidence files matched the observed account and connection state. This final check tested the entire control set together rather than assuming that settings recorded earlier had remained unchanged.

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_0c1guhf7)

### Plain-language proof of the stopped deletion

The deletion attempt targeted CONNECTIONS.md inside /workspace/pineapple/. Auto Review displayed the matching file-deletion rule and required a decision before the action could continue. I selected Deny, so Scout stopped and left CONNECTIONS.md in place.

The preserved file still contained the purpose line, the bank row marked NEVER, and the None row dated 2026-09-15. This provided direct evidence that denying the approval request prevented the file from disappearing. The result did not depend on Scout stating that it had stopped; the retained file and unchanged contents showed the outcome.

### Evidence of Scout's Day 1 boundary

Eleven Ask first rules remained enabled, and no protected action was set to run without approval. Auto Review stayed on, which meant matching actions continued to pause for my decision. The plugin list showed no connected company application, preserving the separation from live business systems.

The connection register recorded no company connection and kept the bank row at NEVER. The usage file contained exactly one line: 2026-09-15 | Plan: Pro | Weekly usage: 1% used. These checks showed that Scout remained inside its declared job, approval, connection, and evidence boundaries at the end of Day 1.

## Documenting the Intact Connection Boundary

![Image](https://nextwork.ai/pineapple_king_overclocked_the_ai/uploads/ff76331a-6372-4488-98d5-6611bf5dec9b_a5y4vn6i)

### Confirming Scout remained within its approved scope

I compared Scout’s final state with the Day 1 boundary. The helper still had one job, its four standing rules remained saved, and Auto Review continued to require my decision for protected actions. No company plugin had been connected during the lab, and the bank restriction remained unchanged.

Both files matched the information observed on the screen. CONNECTIONS.md recorded the absence of company connections, while usage.md retained the single Pro-plan usage entry. The note to Alex Morgan stayed as an unsent draft on the screen. Together, these results showed that Scout completed the allowed recording and drafting work without gaining access to live business tools or sending a message.

## Reflecting on Safe Bot Operations

### Tools and concepts applied

I used Grok Bot, Scout’s standing rules, Auto Review, the plugin list, and two files under /workspace/pineapple/ops/. CONNECTIONS.md recorded the connection purpose, None state, and bank restriction. usage.md recorded the observed Pro plan and weekly usage of 1% used.

The main concepts were narrow job definition, least access, approval before protected action, observed facts instead of guesses, and human control over sending. I also separated instructions from enforcement: standing rules guided Scout, while Auto Review stopped matching actions. The denied delete supplied direct evidence that the approval gate acted before the file changed.

### Project completion experience

I completed the setup and verification in approximately 90 minutes across two sittings. That time covered the control environment, Scout creation, four standing rules, eleven approval rules, connection register, delete test, usage record, founder-directed draft, and final boundary review.

The controls, register, and usage line remained in place when the work ended. The most important outcome was not that Scout drafted a note or wrote files. It was that a protected delete stopped for approval, the denial preserved the file, no company app was connected, and the external message remained unsent inside the learning lab.

### Next learning goal

This practice showed me where Scout’s allowed work ended and where my decision began. I retained the evidence files and approval rules, kept company connections absent, and confirmed that drafting did not become sending. The boundary was visible in both the configuration and the observed delete test.

My next step is to continue testing protected actions without connecting Scout to live business systems. I want each test to use non-sensitive lab data, stop at the approval card, and leave evidence showing what happened after Allow or Deny. Any future connection should require a separate purpose, explicit approval, and a revised connection register before Scout receives access.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/ff76331a-6372-4488-98d5-6611bf5dec9b)*
