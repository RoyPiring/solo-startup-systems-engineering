# Set Up Grok Bot Approval Controls

> Inside the [Solo Startup Systems Engineering](../../README.md) portfolio · *Systems for building and scaling a startup as a solo operator.*

## Overview

I created one Grok Bot helper named Scout for a controlled Day 1 operations lab. Scout could draft content from facts I entered and record only the connections visible on the screen. It could not receive passwords, bank details, real client information, or access to company systems. The work remained under my learning login.

The boundary also kept all external actions under human control. Scout could prepare a message, but it could not send one from this lab. No company app was connected, and the bank connection remained prohibited. This allowed me to test instructions, approval gates, files, and drafting behavior without creating a path into live email, banking, or client tools.

The architecture is built across **7 phases**, anchored by **Establishing a Safe AI Operations Boundary** on the input side and **Documenting the Intact Connection Boundary** at the end. Each phase is listed in the Implementation section below.

## Architecture

```mermaid
---
title: Set Up Grok Bot Approval Controls
---
%%{init: {"theme":"base","themeVariables": {"primaryColor":"#1B4332","primaryTextColor":"#F4D03F","primaryBorderColor":"#F4D03F","secondaryColor":"#264653","tertiaryColor":"#2F5233","lineColor":"#F4D03F","fontFamily":"ui-monospace, SFMono-Regular, Menlo, Consolas, monospace","fontSize":"13px"}}}%%
flowchart TD
    classDef datastore fill:#264653,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef service fill:#1B4332,stroke:#F4D03F,stroke-width:2px,color:#F4D03F
    classDef event fill:#7B42BC,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef io fill:#0d1117,stroke:#F4D03F,stroke-width:1.5px,color:#F4D03F,font-style:italic

    Founder[/The solo founder, who keeps every send and every approval decision/]
    FutureLink[/Any later connection, which has to earn a separate purpose, an explicit approval and a revised register/]

    subgraph Boundary["The boundary, declared before the helper existed"]
        Job{{One job: draft from facts the founder enters, and record only the connections visible on the screen}}
        Never[("Never in scope: passwords, bank details, real client information, access to company systems")]
        NoSend{{Preparing a message is inside the boundary; sending one is not}}
        Learning[(The whole lab runs under a learning login, not a business account)]
    end

    subgraph Pre["Settings checked before the helper was created"]
        Spend(On-demand spending set to None, so the lab authorizes no extra usage charge)
        Review(Auto Review enabled, so a matching action pauses for a decision)
        Plugins(Connected plugin list confirmed empty of any company application)
        FirstNotAfter{{Confirming the controls first is what stops a default setting or an existing connection from quietly widening the helper's reach after creation}}
    end

    subgraph Scout["Scout, and the two controls that are not the same control"]
        Identity[("Named Scout, titled Day 1 operations recorder for Pineapple Advisory")]
        Standing[(Four standing rules describing how it works, attached to the helper and in force in every chat)]
        Rules[(Eleven Ask first rules covering protected actions, with no protected action configured to allow itself)]
        Separate{{Standing rules govern how the helper behaves; Auto Review governs whether a protected action may proceed. Instruction and enforcement are kept apart}}
    end

    subgraph Register["The connection register, as evidence"]
        Conn[("CONNECTIONS.md: a purpose line, the bank row marked NEVER, and a row recording None dated 2026-09-15")]
        NoApp{{No company application was connected at any point, so there was no route into live mail, banking or client tools}}
        Technical{{The missing mail connection enforces the no-send rule technically rather than leaving it to the helper's written instruction}}
    end

    subgraph Gate["The delete gate, tested with a real protected action"]
        Attempt(A real deletion attempt against CONNECTIONS.md inside the workspace folder)
        Card[(Auto Review showed an approval card naming the matching file-deletion rule)]
        Deny(The founder selected Deny)
        Intact[("The file remained, still carrying its purpose line, the NEVER bank row and the None row")]
        NotSelfReport{{The proof is the retained file and its unchanged contents, not the helper stating that it stopped}}
        RealNotExample{{A real protected operation was used rather than a written example, and the evidence file survived the test it was used for}}
    end

    subgraph Usage["The usage record, held to what was on screen"]
        Screen(Usage and Billing read directly: Plan Pro, weekly usage 1% used)
        Line[("usage.md holds exactly one line: 2026-09-15, Plan Pro, weekly usage 1% used")]
        NoGuess{{No heading, no estimated allowance, no limit that the screen did not show. A missing number stays missing}}
        SmallLog{{The file is a small evidence log rather than an account forecast, and its value comes from that refusal}}
    end

    subgraph Draft["A real message, drafted and not sent"]
        Facts(Facts entered by the founder: the workshop moved to Thursday, and one question asking whether Thursday still works)
        Note[(A short note to a named recipient, left on the screen after Scout finished)]
        Stopped{{Scout opened no mail service, selected no recipient and attempted no delivery}}
        Division{{Drafting shapes wording from approved facts; checking the content, choosing the channel and deciding whether it leaves the lab stay with the founder}}
    end

    subgraph Final["The closing check, run against the whole set at once"]
        Recheck(Identity, title, four standing rules, eleven approval rules, Auto Review, plugin list, register and usage file all re-read)
        Held[(Every control still as configured, both files still matching what the screen showed)]
        NotAssumed{{The final check tests the control set together rather than assuming settings recorded earlier had stayed put}}
    end

    subgraph Bounds["What the lab does not claim"]
        OneSide{{Only the Deny path was exercised; nothing here reports what an Allow would have produced}}
        Next{{Further protected actions are to be tested on non-sensitive lab data, each stopping at the approval card and leaving evidence of what followed the decision}}
    end

    Founder -- "opens by declaring" --> Job
    Job -- "bounded by" --> Never
    Job -- "bounded by" --> NoSend
    Job -- "run under" --> Learning
    Never -- "checked first as" --> Spend
    Spend -- "paired with" --> Review
    Review -- "paired with" --> Plugins
    Plugins -- "together give" --> FirstNotAfter
    FirstNotAfter -- "only then creating" --> Identity
    Identity -- "carries" --> Standing
    Identity -- "carries" --> Rules
    Review -- "enforces" --> Rules
    Standing -- "held apart from Auto Review by" --> Separate
    Rules -- "held apart from the standing rules by" --> Separate
    Identity -- "records into" --> Conn
    Plugins -- "evidenced by" --> NoApp
    Conn -- "records" --> NoApp
    NoApp -- "is what gives" --> Technical
    Conn -- "targeted by" --> Attempt
    Attempt -- "matched a rule, raising" --> Card
    Rules -- "is what Card names" --> Card
    Card -- "answered by" --> Deny
    Deny -- "left" --> Intact
    Intact -- "establishes" --> NotSelfReport
    Attempt -- "chosen deliberately, giving" --> RealNotExample
    Intact -- "is why" --> RealNotExample
    Identity -- "also reads" --> Screen
    Screen -- "written as" --> Line
    Line -- "constrained by" --> NoGuess
    NoGuess -- "makes it" --> SmallLog
    Founder -- "supplies" --> Facts
    Facts -- "drafted into" --> Note
    Note -- "went no further, because" --> Stopped
    Technical -- "is what backs" --> Stopped
    Stopped -- "preserves" --> Division
    Division -- "returns the decision to" --> Founder
    Intact -- "re-read by" --> Recheck
    Line -- "re-read by" --> Recheck
    Note -- "re-read by" --> Recheck
    Recheck -- "found" --> Held
    Held -- "earned by" --> NotAssumed
    Held -- "bounded by" --> OneSide
    OneSide -- "answered next by" --> Next
    Next -- "gates" --> FutureLink
    NoApp -- "stays absent until" --> FutureLink

    class Never,Learning,Identity,Standing,Rules,Conn,Card,Intact,Line,Note,Held datastore
    class Spend,Review,Plugins,Attempt,Deny,Screen,Facts,Recheck service
    class Job,NoSend,FirstNotAfter,Separate,NoApp,Technical,NotSelfReport,RealNotExample,NoGuess,SmallLog,Stopped,Division,NotAssumed,OneSide,Next event
    class Founder,FutureLink io
```

The diagram shows the topology and data flow of the system as built. The full architectural narrative, with screenshots and prose, lives in [`documents/grok-bot-approval-controls.md`](./documents/grok-bot-approval-controls.md).

## Implementation

This system is built across **7 phases**:

1. **Establishing a Safe AI Operations Boundary**
2. **Preparing Grok Bot for Controlled Work**
3. **Building Scout's Day 1 Control Set**
4. **Proving the Delete Gate and Recording Usage**
5. **Drafting a Real Message While Keeping Sending Human-Controlled**
6. **Verifying the Complete Day 1 Control Set**
7. **Documenting the Intact Connection Boundary**

For the full walkthrough with screenshots and step-by-step content, see [`documents/grok-bot-approval-controls.md`](./documents/grok-bot-approval-controls.md).

## Validation

Each build phase below is documented in [`documents/grok-bot-approval-controls.md`](./documents/grok-bot-approval-controls.md), with screenshots, configuration, and notes as captured during the build:

- ✅ Establishing a Safe AI Operations Boundary
- ✅ Preparing Grok Bot for Controlled Work
- ✅ Building Scout's Day 1 Control Set
- ✅ Proving the Delete Gate and Recording Usage
- ✅ Drafting a Real Message While Keeping Sending Human-Controlled
- ✅ Verifying the Complete Day 1 Control Set
- ✅ Documenting the Intact Connection Boundary
