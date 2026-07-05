# Dispute a Charge: Claude Skills

Get your money back. These are [Claude](https://claude.ai) skills that turn a wrong charge, junk fee, or refused refund into a letter the company actually has to take seriously.

Most people lose this money not because they lack a case, but because the message they send is a polite complaint instead of one that names the actual legal mechanism, sets a deadline, and shows the company what happens if they ignore it. These skills know those mechanisms, verified against the real rules, and write the letter for you.

There are four editions, one for each legal system:

| Edition | For you if you're... | Built around |
|---|---|---|
| **`dispute-charge`** | In the **United States** | Fair Credit Billing Act, Regulation E, ROSCA, No Surprises Act |
| **`dispute-charge-in`** | In **India** | RBI zero-liability rules, UPI dispute framework, Consumer Protection Act 2019, RBI Ombudsman |
| **`dispute-charge-eu`** | In an **EU country** (or Norway/Iceland) | Right of withdrawal, legal guarantee of conformity, ECC-Net |
| **`dispute-charge-uk`** | In the **United Kingdom** | Section 75, chargeback, Consumer Rights Act 2015, Financial Ombudsman |

---

## What it does

You tell Claude what happened, "they charged me twice," "I cancelled but got billed," "this hotel hit me with a fee I was never told about", and the skill:

1. **Asks for the few facts that matter** (the exact charge, the date, how you paid, what you've already tried) if you haven't already given them. Specific letters get refunds; vague ones get form replies.
2. **Picks the right mechanism** for your situation, a credit-card billing dispute is a different lever than a debit-card claim, a faulty product, or a subscription you cancelled.
3. **Writes a ready-to-send letter**, one page, calm, specific, with the right legal basis named, a deadline, and the escalation step (the regulator or ombudsman) made visible.

You copy it, send it, and have a real shot at getting your money back.

## What makes it different from just asking an AI

Consumer-protection rules are exactly the kind of thing a language model gets *almost* right, and almost right is dangerous, because a confidently wrong legal citation undermines your case. Every mechanism in these skills was checked against current sources. A few examples of what that caught:

- The US edition does **not** cite the FTC "click-to-cancel" rule, because a federal court **vacated it in July 2025**. It uses what's actually in force instead.
- The India edition is built around the RBI rule most people have never heard of: report an unauthorized transaction within **3 working days** of the bank's alert and your liability is **zero**, the bank must provisionally credit the amount within 10 working days. It also knows the ₹100-per-day compensation for delayed failed-transaction reversals, and that courts have rejected the "it was OTP-verified so you authorized it" defense.
- The EU edition keeps the **14-day cooling-off right** (for changing your mind) separate from the **2-year legal guarantee** (for faulty goods), two rights people constantly confuse and apply to the wrong situation.
- The UK edition gets the Section 75 band right (£100.01–£30,000, single item), including the rule that paying even **1p** of the price on a credit card covers the whole purchase.

The skills are also built to **refuse to help fabricate a dispute**. The whole strategy depends on a truthful, documented account; disputing in bad faith can be fraud. If you don't have grounds, the skill will tell you, and point you to the disputes you do have.

## Installing

These are Claude Skills, packaged as `.skill` files.

1. Download the `.skill` file for your region from this repo (or from the [Releases](../../releases) page):
   - `dispute-charge.skill`. US
   - `dispute-charge-in.skill`. India
   - `dispute-charge-eu.skill`. EU
   - `dispute-charge-uk.skill`. UK
2. In Claude, go to **Settings → Capabilities → Skills** and upload the file. (Skill availability depends on your Claude plan; see Anthropic's documentation for where Skills are supported.)
3. Start a chat and describe your situation. The skill triggers on its own, you don't have to name it.

You can also just open the `SKILL.md` and reference files in this repo and read them directly; they're plain Markdown and double as a consumer-rights guide.

## How to talk to it

You don't need special phrasing. All of these work:

> "A subscription charged me $40 after I cancelled. How do I get it back?"

> "Bought a laptop online for £600, it arrived faulty, the shop is ignoring me."

> "Hotel charged me €150 for a 'cleaning fee' I was never told about. I want to dispute it."

> "My bank let through a payment I never made, what do I do?"

> "₹8,000 got debited by UPI but the transaction failed, and it's been four days with no reversal."

If you already have all the details, it writes the letter straight away. If not, it asks a couple of quick questions first, then writes it.

## What's inside each edition

Each skill is a `SKILL.md` (the strategy and letter structure) plus a set of reference files Claude reads as needed for your specific situation, for example, the US edition has separate references for credit cards, debit/bank, medical bills, subscriptions, travel/service, and an international fallback. You can browse them all in the [`/`](.) directory of each edition's folder.

## Scope and honest limits

- These skills produce **strong first-step letters**, not legal representation. For large sums, anything heading to court, or debt already in collections, they'll say so and point you to the right professional or agency (Citizens Advice, a consumer attorney, your national consumer authority, the relevant ombudsman).
- Consumer law **changes**, and national rules within the EU **vary**. The skills lean on stable, EU/federal-level mechanisms and tell you to confirm country-specific details with your local authority rather than guessing.
- Nothing here is legal advice, and outcomes aren't guaranteed. What's guaranteed is that you'll send a far better letter than the one most people send.

## Contributing

Spotted an out-of-date rule, a threshold that's changed, or a mechanism worth adding (a new country edition, a companion skill for filing the regulator complaint when the first letter is ignored)? Open an issue or a pull request. Accuracy is the whole point of this project, so corrections with a source are especially welcome.

## License

See [LICENSE](LICENSE).

---

*These skills are an independent project and are not affiliated with or endorsed by any government agency, regulator, or ombudsman service. They help you write your own letters; they do not act on your behalf.*
