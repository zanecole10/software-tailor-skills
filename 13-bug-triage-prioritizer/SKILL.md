---
name: bug-triage-prioritizer
description: Triage bug reports by severity, recommend fix order, generate client communication templates, determine whether to charge for fixes, and provide Claude Code prompts to resolve issues quickly.
---

# Bug Triage & Fix Prioritizer

Handle bugs professionally. Keep clients happy post-launch.

## What This Skill Does

Input: Bug reports from client
Output: Severity levels, fix priority order, client communication templates, fix-or-charge decision, Claude Code prompts

## Bug Severity Levels

### 🔴 CRITICAL (Fix immediately)
- Software completely unusable
- Data loss or corruption
- Security vulnerability
- Major feature completely broken

**Response Time:** Within 4 hours
**Communication:** Call + email immediately
**Charge:** Never (part of warranty)

**Examples:**
- Users can't log in
- Database corruption
- Payment processing failing
- Data breach

---

### 🟠 HIGH (Fix within 24 hours)
- Major feature partially broken
- Significant user workflow disrupted
- Affects most users

**Response Time:** Within 24 hours
**Communication:** Email with timeline
**Charge:** Usually not (within 30-day warranty)

**Examples:**
- PDF reports not generating
- Search functionality broken
- Photos won't upload

---

### 🟡 MEDIUM (Fix within 1 week)
- Minor feature broken
- Workaround exists
- Affects some users sometimes

**Response Time:** 3-5 business days
**Communication:** Email acknowledgment + fix date
**Charge:** Depends (after 30 days, may charge)

**Examples:**
- Dropdown not sorting correctly
- Email notifications delayed
- UI element misaligned

---

### 🟢 LOW (Fix in next update)
- Cosmetic issues
- Minor inconvenience
- Rare edge case

**Response Time:** Next scheduled update
**Communication:** "Added to backlog"
**Charge:** Usually yes (after warranty)

**Examples:**
- Button color wrong
- Typo in label
- Feature request (not a bug)

---

## Fix or Charge Decision Tree

**Free Fixes (Within 30-Day Warranty):**
✅ Software doesn't work as specified
✅ Critical or High severity
✅ You introduced the bug (your mistake)
✅ Affects core functionality

**Charge for Fixes:**
💵 After 30-day warranty period
💵 User error (not a bug)
💵 Low severity cosmetic issues
💵 New feature request disguised as "bug"
💵 Scope creep ("I thought it would also do X")

## Client Communication Templates

### Critical Bug Response

Subject: [URGENT] Investigating [Issue] - ETA 4 hours

"Hi [Client],

I just saw your report about [issue]. This is my top priority right now.

I'm investigating the cause and will have a fix deployed within 4 hours.

I'll update you every hour until it's resolved.

Apologies for the disruption.

[Your Name]"

---

### High/Medium Bug Response

Subject: Bug Report Received - Fix Timeline

"Hi [Client],

Thanks for reporting [issue]. I've triaged this as [severity level].

**What's happening:** [brief explanation]
**Fix timeline:** [specific date/time]
**Workaround (if any):** [temporary solution]

I'll notify you as soon as it's fixed.

[Your Name]"

---

### Low Priority Bug Response

Subject: [Issue] Added to Backlog

"Hi [Client],

Thanks for reporting [issue]. This is a minor cosmetic issue that doesn't affect functionality.

I've added it to the backlog and will include the fix in the next monthly update.

If this is more urgent than I'm understanding, let me know and I can prioritize it (may require additional development hours).

[Your Name]"

---

## Handling "Why Isn't This Free?" Conversations

**Client:** "I'm paying you $15K and there are still bugs?!"

**Response:**
"I completely understand the frustration. Here's the situation:

This [bug type] is a [severity level] issue that [impact description].

**It's covered under warranty** because [reason: affects core functionality / within 30 days / my oversight].

I'm fixing it at no charge and will have it resolved by [date].

What's NOT covered:
- Issues after the 30-day warranty
- New feature requests
- Changes to how features work (vs. fixing broken features)

Does that make sense?"

## Prevention Strategy

**Include in contract:**
- 30-day bug fix warranty
- Definition of "bug" vs. "feature request"
- Response time commitments
- Post-warranty support options

**This prevents:**
- "Why am I paying for bug fixes?"
- Endless free work disguised as "bugs"
- Scope creep through bug reports

## Remember

Bugs happen. How you handle them defines your professionalism.

- **Respond fast** (even if fix takes time)
- **Communicate clearly** (set expectations)
- **Fix critical issues immediately** (protect your reputation)
- **Charge for scope creep** (protect your time)

Handle bugs well = clients trust you = referrals + recurring revenue
