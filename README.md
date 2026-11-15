#  User Access Review

## 🎫 The Ticket

It's 5 October 2026, my first day on the security team at Northwind Health, a fictional healthcare organisation with about 400 clinics.

My first ticket arrives. The IT Manager writes:

> We've never properly reconciled the patient admin portal against HR. Here are both exports. Tell me what's wrong, what to fix first, and how we stop it happening again.

<br>

**Supporting Information:** [HR Export & Patient Admin Portal Users](Documents/01.%20Source%20Data.md)

<BR><BR>

<table>
<tr>
<td>

### 🛡️ Decision

**Confirm whether `treyes` is still authorised. If not, disable the account.**

The contractor's contract ended on 31 July 2026, but the account was used with administrator access on 28 September.

**2 of 7 accounts** were used after their end dates. `treyes` is the highest priority because administrator access poses a greater security risk.

**Other six accounts:** [Findings & Recommendations](https://github.com/itsanitarose/Access-Review/blob/main/Documents/02.%20Findings%20%26%20Recommendations.md)

</td>
</tr>
</table>

<BR>

The review flagged two critical accounts, with continued administrative access presenting the greatest risk. I needed to assess the potential impact before recommending action.

<BR>

## What's the Risk?

The patient admin portal contains sensitive information. Access that no longer matches someone's responsibilities puts **patient data at risk**, but removing it without checking could **disrupt legitimate work** and **business operations**.

I need to understand what the records show and what still needs checking before recommending action.

<br>

## The Investigation

### 1. Does the account match HR?

I started with employment status, contract end dates and recent login activity. If someone has left but their account remains active, that needs investigating.

### 2. Is the access still appropriate?

Finding a matching HR record didn't mean the permissions were right. I checked access levels, administrative privileges and shared credentials against job responsibilities, looking for access that appeared excessive or difficult to attribute to an individual.

### 3. What needs further investigation?

Some accounts couldn't be assessed from the exports alone. I needed to establish who owned the account, whether the access had been approved and whether it was still required.

For suspicious login activity, I would need authentication and application audit logs to establish what happened, alongside approval records to determine whether the access was authorised.

### 4. What needs attention first?

I ranked the findings by risk, considering the privileges involved, the evidence available and the potential consequences of misuse.
I also considered the impact of restricting access that might still be legitimate. Not every discrepancy required the same response.

<br>

## What I Found

The review covered seven accounts.

| Severity | Accounts | Finding |
|---|---:|---|
| 🔴 Critical | 2 | Login activity after employment or contract end dates |
| 🟠 High | 2 | Orphaned admin account and shared credentials |
| 🟡 Medium | 2 | Extended leave and Finance access requiring review |
| 🟢 Low | 1 | Engineering admin access requiring justification |
| **Total** | **7** | |

<br>

## Decisions & Recommendations

Two accounts were rated Critical, so I needed to decide which required attention first.

The contractor's recorded end date was 31 July 2026, but the portal export showed an Admin login on 28 September 2026. Almost two months later, the account still had administrative access.

I prioritised `treyes` because those privileges increased the potential impact of misuse.

My **recommendation** was to confirm whether the contract had been extended and continued access approved. I'd check HR and manager approvals, verify the need for Admin privileges and request the login logs. If the access couldn't be justified, I'd recommend disabling the account and investigating the activity.

But there's a point I don't want to overlook. The contract might have been extended without HR being updated. That would point to a governance gap that needs correcting.

And one thing remains uncertain: the exports don't tell me who logged in or what they did.

Explore the [findings and recommendations](Documents/02.%20Findings%20%26%20Recommendations.md) for the remaining six accounts.

<br>

## Looking Back at the Review

Starting with the HR reconciliation was the right call. It gave me a baseline of who should have access versus who actually had access according to the portal records.

It's incredibly easy to "panic disable" a privileged account with activity after its contract end date. My instinct to pause rather than immediately smashing the "disable account" button came down to operational awareness.

Acting too quickly can cause problems. Disabling access someone still needs can disrupt their work without fixing the real issue, so I needed to understand the situation before deciding what to do. That wasn't something the records showed, but it was a possibility I needed to check, while treating the access risk as a priority.

Reading the NIST guidance helped me anchor that restraint. It allowed me to slow down and establish what needed confirming before recommending a disruptive change.


I also explored Microsoft's guidance on dormant and shared accounts, alongside [NHS England's approach](https://www.england.nhs.uk/long-read/smartcards-and-access-controls/#other-leavers) to extended leave, which I found particularly interesting for how large organisations manage extended leave and temporary changes in access.

<br>

## What I Will Improve Next Time

When I reached a blind spot in the records, I researched what needed confirming and made a recommendation. Looking back, I could have been more precise.

For `treyes`, my first draft recommended investigating the login activity, but didn't specify which evidence to request or what questions it needed to answer.

Next time, I'll define those steps earlier and more precisely, rather than leave the investigation as a broad recommendation.



<br>



## Explore the Investigation

| Document | What's Inside |
|---|---|
| [01. HR Export & Patient Admin Portal Users](Documents/01.%20HR%20Export%20%26%20Patient%20Admin%20Portal%20Users.md) | Original HR records and patient portal export |
| [02. Findings & Recommendations](Documents/02.%20Findings%20%26%20Recommendations.md) | Access discrepancies, risk ratings and proposed actions |
| [03. Preventive Controls](Documents/03.%20Preventive%20Controls.md) | Recommendations to prevent recurring access issues |
| [04. IT Manager Summary](Documents/04.%20Summary%20for%20the%20IT%20Manager.md) | Key findings and recommended priorities |



<br>

---

[All Case Studies](https://github.com/itsanitarose/IAM-Case-Studies) · [Week 2: Permission Sprawl & RBAC →](https://github.com/itsanitarose/IAM-Permission-Sprawl-RBAC)

*<sub>Northwind Health is fictional. This is independent work. No production systems were changed.</sub>*


