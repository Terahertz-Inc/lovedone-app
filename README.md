# lovedone.app

**One inbox for Mom's care.**

Loved One is the family-caregiver surface of the Sandwich platform.
Give Mom's doctors, pharmacies, insurers, and attorneys **one private
email address**, and every message they send about her care lands in
one place — where the whole family can see it, instead of getting lost
in one sibling's personal inbox.

💌 **Get your inbox:** [lovedone.app](https://lovedone.app)
👨‍👩‍👧 **Family app:** [app.joinsandwich.com](https://app.joinsandwich.com)
🌐 **Parent company:** [joinsandwich.com](https://www.joinsandwich.com)
📚 **Full docs:** [docs.joinsandwich.com](https://docs.joinsandwich.com)
🐙 **Sister repo:** [Terahertz-Inc/sandwich-public](https://github.com/Terahertz-Inc/sandwich-public)

> This is a public, README-only repo. The live landing page is
> [lovedone.app](https://lovedone.app); the family app lives at
> [app.joinsandwich.com](https://app.joinsandwich.com).

---

## What is the Family Inbox?

The "sandwich generation" — adults caring for an aging parent while
raising kids — coordinates Mom's healthcare across **discharge
summaries, pharmacy refills, cardiology reminders, insurance EOBs, and
attorney correspondence**. Today those messages land in one sibling's
personal inbox, and the rest of the family is in the dark.

The Family Inbox fixes that with **one shared address per loved one**:

- Every loved one gets a **private, dedicated email address** on
  `lovedone.app`.
- The whole family (siblings, partners, the loved one themselves)
  sees what arrives in real time.
- The address is grounded in HIPAA's
  [personal-representative doctrine (45 CFR §164.502(g))](https://www.hhs.gov/hipaa/for-professionals/privacy/guidance/personal-representatives/index.html) —
  providers must honor a designated confidential-communications
  address. Zero institutional cooperation required.

---

## The address format

Every loved one gets an address shaped like a name plus a zipcode, so
it's easy to dictate to a hospital intake clerk:

```
{first_name}-{3 letters}{2 digits}@lovedone.app
```

Examples:

- `helen-MKR47@lovedone.app`
- `robert-QPL23@lovedone.app`

Say it out loud: *"Helen, dash, M-K-R, four-seven, at loved-one-dot-app."*

The 5-char code uses **24 letters (no O or I) + 2 digits** — 1.38
million combinations per first name. Plenty of headroom, no
visually-confusable characters, no PII leaked into mail headers.

**Privacy mode** swaps the first name for a neutral noun for situations
where a name leak would be uncomfortable (estranged family, dementia,
public figures): `meadow-MKR47@lovedone.app`.

---

## How it works

1. **Sign up** in the family app at
   [app.joinsandwich.com](https://app.joinsandwich.com) and add your
   loved one. An inbox address is generated instantly — no
   configuration needed.
2. **Tell her providers** — give the address as a second contact email
   at every doctor, pharmacy, insurer, and attorney. Sandwich provides
   a printable wallet card and a letter-to-providers PDF to make this
   easy.
3. **The whole family sees what arrives.** Invite your siblings;
   assign roles (owner, coordinator, viewer). Every new message has an
   AI-generated one-line summary and category (appointment, pharmacy,
   billing, discharge) so you can triage at a glance.

Two flows for involving the loved one:

- **Option A — Add as second email.** Helen gives providers this
  address alongside her personal email. They CC both. Helen keeps
  reading her own inbox; the family gets a copy.
- **Option B — Primary with forwarding.** Providers send only here.
  Sandwich auto-forwards each message to Helen's Gmail so her
  experience doesn't change — but the family also sees what arrives.

---

## Why a separate domain

`lovedone.app` is the **family caregiver** surface;
[`joinsandwich.com`](https://www.joinsandwich.com) (and the
[Terahertz-Inc/sandwich-public](https://github.com/Terahertz-Inc/sandwich-public)
repo) is the **developer / corporate** surface — Sandwich MCP, Sandwich
Pipe, Sandwich Soft.

Keeping the consumer surface on its own domain means:

- The address `helen-MKR47@lovedone.app` reads as obviously about a
  loved one's care — not a B2B platform.
- Providers entering it in an alternate-contact field aren't routed
  through corporate marketing pages.
- The brand feels approachable in the emotionally heavy moments when
  it shows up in someone's inbox.

The two surfaces share one backend, one auth, and one set of
[docs](https://docs.joinsandwich.com).

---

## Related repos and surfaces

- 🐙 [**Terahertz-Inc/sandwich-public**](https://github.com/Terahertz-Inc/sandwich-public) —
  the parent Sandwich platform: developer docs, two MCP servers
  ([directory](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.joinsandwich) +
  [care-circle](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.joinsandwich)),
  Sandwich Pipe, Sandwich Soft.
- 👨‍👩‍👧 [app.joinsandwich.com](https://app.joinsandwich.com) — the
  family workspace. Each loved one's inbox lives at
  `app.joinsandwich.com/inbox/{lovedOneId}`.
- 🌐 [joinsandwich.com](https://www.joinsandwich.com) — marketing /
  corporate site.
- 📚 [docs.joinsandwich.com](https://docs.joinsandwich.com) — the
  technical hub for the whole stack.
- 🤖 [app.joinsandwich.com/agents](https://app.joinsandwich.com/agents) —
  agent / MCP integration guide for the whole platform.

---

## FAQ (short)

**Will providers accept this?**
Yes. Every EHR, pharmacy, and patient-intake form already has an
"alternate contact email" field. You're just filling it with a better
value — no new workflow, no new system.

**Does Mom have to give up her existing email?**
No. Providers can keep sending to Mom's personal email too (Option A),
or send only here and we auto-forward to her Gmail (Option B).

**Can I change the inbox address?**
Addresses are generated once and preserved indefinitely. Providers
have it in their systems for years. If you need to rotate (e.g., a
compromised address), the old one forwards for 90 days, then stops.
Old messages are always preserved.

---

## License

© Loved One / Sandwich / Terahertz Inc.
