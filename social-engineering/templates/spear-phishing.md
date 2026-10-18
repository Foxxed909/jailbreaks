# Spear Phishing Templates

Targeted phishing — personalized to the specific victim using OSINT data.

---

## AI Generation Prompt

Feed this to any capable LLM with OSINT data filled in:

```
Write a convincing spear phishing email targeting [target name], a [job title] at [company].

OSINT data:
- LinkedIn: [summary of their profile]
- Recent company news: [relevant news]
- Known colleagues: [names]
- Technologies they use: [from job postings / LinkedIn]
- Recent activity: [conference talks, published articles, etc.]

Goal: Get them to click a link / open an attachment / provide credentials
Pretext: [choose: IT security alert / vendor invoice / HR communication / executive request]
Urgency level: [low / medium / high]
Tone: [formal / semi-formal]

Include: subject line, email body, call to action
```

---

## Template: IT Security Alert

```
Subject: [URGENT] Unusual sign-in detected on your account — action required

Dear [First Name],

Our security systems have detected an unusual sign-in attempt on your [Company] account 
from an unrecognized device in [foreign location].

If this was you, no action is needed. If this was NOT you, your account may be 
compromised. Please verify your identity immediately:

[VERIFY MY ACCOUNT →]

This link expires in 24 hours. If you do not verify, your account access will be 
temporarily suspended to protect company data.

IT Security Team
[Company Name]
```

---

## Template: Executive Request (BEC)

```
Subject: Quick request — confidential

Hi [Target],

Are you available? I need a favor handled quickly and discreetly before [deadline].
I'm in back-to-back meetings and can't take calls.

Details once you confirm you can help.

[Executive Name]
Sent from mobile
```

*(Follow-up: request wire transfer, gift cards, or credential sharing once target confirms.)*

---

## Personalization Variables

The more you fill in, the more convincing:
- First name (always use it — familiarity increases click rate)
- Company name (appears legitimate)
- Their manager's name (authority + familiarity)
- Recent company event (conference, acquisition, product launch)
- Their technology stack (reference specific tools they use)
- Their location (local time zone, local banking details if relevant)
