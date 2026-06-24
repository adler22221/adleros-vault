---
aliases: []
type: literature
project: master-thesis
status: ai-draft
citation-status: citable
topic: [hobbes, locke, hume, empiricist-pole, self-authorization, self-preservation, ontological-freedom, ch4]
source-notes:
  - "Thomas Hobbes, Leviathan (1651). Source: Project Gutenberg eBook #3207 — cached at P:\\_AI agents\\full-research-workflow\\.research\\cache\\ch4-oa\\hobbes_leviathan_pg3207.txt. Tier used: OA (Tier 4 — local cache). NLM attempted; auth expired after 1 try, abandoned per cascade rule."
  - "John Locke, Two Treatises of Government (1689), Second Treatise. Source: Project Gutenberg, cached at .research/cache/ch4-oa/locke_2nd_treatise.txt. Tier used: OA (Tier 4 — local cache)."
  - "John Locke, An Essay Concerning Human Understanding (1689). Source: Project Gutenberg eBook #10615 — cached at .research/cache/ch4-oa/locke_essay_pg10615.txt. Tier used: OA (Tier 4 — local cache)."
  - "David Hume, A Treatise of Human Nature (1739–40). Source: Project Gutenberg eBook #4705 — cached at .research/cache/ch4-oa/hume_treatise_pg4705.txt. Tier used: OA (Tier 4 — local cache)."
  - "David Hume, An Enquiry Concerning Human Understanding (1748). Source: Project Gutenberg eBook #9662 — cached at .research/cache/ch4-oa/hume_enquiry_pg9662.txt. Tier used: OA (Tier 4 — local cache)."
  - "Companion dossier read (not re-pulled): ch4-adorno-horkheimer-self-preservation-T0-2026-06-05.md"
summary: "Verbatim T0 dossier on the empiricist strand of Enlightenment thought (Hobbes, Locke, Hume) organized by Q1–Q4: ground of self-authorization, stance toward given limits, presence/absence of 存在論的自由, and self-preservation as engine of enlightenment reason (A&H cross-reference). All passages verbatim from Project Gutenberg OA texts. NLM auth expired after one attempt; cascade fell through to local OA cache. Includes synthesis table."
---

# T0 Verbatim Dossier: The Empiricist Pole — Self-Authorization, Limits, and Self-Preservation
**Authors covered:** Thomas Hobbes (*Leviathan*, 1651) · John Locke (*Second Treatise of Government*, 1689; *Essay Concerning Human Understanding*, 1689) · David Hume (*Treatise of Human Nature*, 1739–40; *Enquiry Concerning Human Understanding*, 1748)
**Access method:** All texts from Project Gutenberg OA files, locally cached at `.research/cache/ch4-oa/`. Passages extracted verbatim with PowerShell string indexing; section identities confirmed against chapter/section headers found in the same files.
**NLM status:** A-Sources notebook (`c68ca15e`) queried; auth expired immediately, abandoned after one attempt per cascade rule. No NLM passages used.
**Companion dossier:** A&H self-preservation passages cited by page from `ch4-adorno-horkheimer-self-preservation-T0-2026-06-05.md`; not re-pulled.

Related: [[master-thesis]] [[squeeze-ontology]]

---

> ## ⚠️ GLOSSARY RECONCILIATION (added 2026-06-05 — read before using any Uegaki-term analysis below)
>
> The **verbatim Hobbes/Locke/Hume passages (Q1–Q2) are sound and Uegaki-independent** — use them freely. But this dossier's **Q3 ("Anything like 存在論的自由?"), Q4 (self-preservation-as-engine), and the synthesis-table columns** were framed BEFORE the authoritative glossary (`uegaki-glossary-yugen-mugen-no-sei-16-18-verbatim-2026-06-05.md`, which completed *last*) and are **SUPERSEDED by it**:
>
> 1. **存在論的自由 (glossary 16-08) is a STANCE, not a metaphysical property.** It is the normative position that the human "ought to be freed from ALL external forces determining its existence (存在論的抑圧) and self-determine its mode of being," and decisively it is the **EXPANSION of 政治的自由 (political freedom) generalized to existence-as-such** — Kant's 意志の自律 the hinge, Marx the peak. So the dossier's question ("does this thinker's metaphysics yield a *self answerable to nothing given*?") is the wrong question; the right one is "does this thinker hold/enable the *political→ontological expansion*?"
> 2. **Locke is repositioned.** Locke (with Rousseau) = the 自由の人間学, supplying its two PREMISES — 時空間的自立性 (16-04) + 約束された本来性 (16-05) — at the **political-freedom stage**. 存在論的自由 is the *later* expansion (Kant→Marx). Locke is therefore the **founder of the premises, NOT a holder of 存在論的自由**; "Locke yields 存在論的自由 via self-ownership" is imprecise — self-ownership is the *premise*, the ontological expansion is post-Locke.
> 3. **存在論的抑圧 (16-09) = the social/traditional/relational "iron chains"** (traditions, customs, attribute-stereotypes, the authority/power inside relationships) framed as illegitimate *from the 存在論的自由 stance* — NOT threats to self-preservation. So **obstruction of self-preservation/appetite is NOT 存在論的抑圧** in Uegaki's sense; the empiricist self-preservation driver does **not** by itself generate 存在論的自由/抑圧.
> 4. **無限の生 (16-02) = the limitless *actualization* of an imagined ideal upon reality** ("想像された理念を際限なく現実化させられること") — explicitly **NOT "eternal life,"** and not merely "denial of the given." Q4's "self-preservation = engine of 無限の生" must be re-read: per A&H, self-preservation is the engine of **instrumental reason = the actualization MEANS**; it does NOT constitute the 無限の生 *worldview* (the idealist ideal). The two **converge at the apparatus stage**, not at the level of the empiricists' own claims.
>
> **Net:** keep the verbatim; treat the Q3/Q4 Uegaki-linkage and the table's "Yields 存在論的自由?" / "Self-preservation = engine?" columns as superseded by the four points above. The corrected linkage belongs in the synthesis.

---

## PART I — THOMAS HOBBES (*Leviathan*, 1651)

**Locus conventions:** Chapter numbers follow Hobbes's own Roman numerals (CHAP. XIV, etc.) as they appear in the PG text. No standard page-number apparatus applies to PG plain text; loci are given as chapter + section header exactly as they appear in the file.

---

### Q1 — Ground of Self-Authorization

#### 1a. Right of Nature defined: liberty for self-preservation (Ch. XIV, "Right Of Nature What")

> "The RIGHT OF NATURE, which Writers commonly call Jus Naturale, is the Liberty each man hath, to use his own power, as he will himselfe, for the preservation of his own Nature; that is to say, of his own Life; and consequently, of doing any thing, which in his own Judgement, and Reason, hee shall conceive to be the aptest means thereunto."

*(Hobbes, Leviathan, Ch. XIV, "Right Of Nature What"; PG #3207.)*

**Evidence note:** The right of nature is grounded not in reason as divine participation or in social contract, but in the brute fact of embodied life requiring its own continuation. "His own Judgement, and Reason" are purely instrumental — they determine the "aptest means" to preservation, not the content or the end. The end (self-preservation) is given by nature, not derived from reason. Self-authorization is therefore appetitive and survival-based, not rational in the Kantian or theological sense.

---

#### 1b. Liberty defined: absence of external impediments (Ch. XIV, "Liberty What"; Ch. XXI, "Liberty What")

**Ch. XIV:**

> "By LIBERTY, is understood, according to the proper signification of the word, the absence of externall Impediments: which Impediments, may oft take away part of a mans power to do what hee would; but cannot hinder him from using the power left him, according as his judgement, and reason shall dictate to him."

*(Hobbes, Leviathan, Ch. XIV, "Liberty What"; PG #3207.)*

**Ch. XXI (extended definition):**

> "Liberty, or FREEDOME, signifieth (properly) the absence of Opposition; (by Opposition, I mean externall Impediments of motion;) and may be applyed no lesse to Irrational, and Inanimate creatures, than to Rationall. For whatsoever is so tyed, or environed, as it cannot move, but within a certain space, which space is determined by the opposition of some externall body, we say it hath not Liberty to go further."

> "And according to this proper, and generally received meaning of the word, A FREE-MAN, is 'he, that in those things, which by his strength and wit he is able to do, is not hindred to doe what he has a will to.'"

*(Hobbes, Leviathan, Ch. XXI, "Liberty What" / "What It Is To Be Free"; PG #3207.)*

**Evidence note:** Liberty is defined mechanically — as the absence of external stoppage. This is not freedom as self-determination in any positive sense (not Kantian autonomy, not Rousseauian general will). A free person is simply one who is not blocked from doing what their will drives them toward. The definition applies equally to water flowing in a channel and to human agents. This radically de-spiritualizes freedom: it is a property of motion, not of rational faculty.

---

#### 1c. Will = the last appetite in deliberation (Ch. VI, "The Will")

> "In Deliberation, the last Appetite, or Aversion, immediately adhaering to the action, or to the omission thereof, is that wee call the WILL; the Act, (not the faculty,) of Willing. And Beasts that have Deliberation must necessarily also have Will. The Definition of the Will, given commonly by the Schooles, that it is a Rationall Appetite, is not good. For if it were, then could there be no Voluntary Act against Reason. For a Voluntary Act is that, which proceedeth from the Will, and no other."

*(Hobbes, Leviathan, Ch. VI, "The Will"; PG #3207.)*

**Evidence note:** Hobbes explicitly rejects the scholastic definition of will as "rational appetite." Will is the last appetite to prevail in a sequence of competing desires and aversions — it is constitutively pre-rational. This forecloses the standard rationalist move (Kant, Descartes) of grounding self-authorization in reason's legislative capacity. The ground is appetite — itself a form of motion toward objects — not rational self-legislation.

---

#### 1d. Appetite/desire: the basic structure (Ch. VI, "Endeavour; Appetite; Desire")

> "This Endeavour, when it is toward something which causes it, is called APPETITE, or DESIRE; the later, being the generall name; and the other, oftentimes restrayned to signifie the Desire of Food, namely Hunger and Thirst. And when the Endeavour is fromward something, it is generally called AVERSION."

> "Of Appetites, and Aversions, some are born with men; as Appetite of food, Appetite of excretion, and exoneration… The rest, which are Appetites of particular things, proceed from Experience, and triall of their effects upon themselves, or other men."

*(Hobbes, Leviathan, Ch. VI, "Endeavour; Appetite; Desire…"; PG #3207.)*

**Evidence note:** Appetite is defined as micro-motion (endeavour) oriented toward an object. The base appetites are innate (food, excretion); derivative appetites are formed through experience. This is empiricist psychology: the self is constituted from the bottom up by appetitive motions and their experiential modifications, not from any innate rational form.

---

#### 1e. "Power after power" — the restless desire (Ch. XI, "A Restlesse Desire Of Power, In All Men")

> "So that in the first place, I put for a generall inclination of all mankind, a perpetuall and restlesse desire of Power after power, that ceaseth onely in Death. And the cause of this, is not alwayes that a man hopes for a more intensive delight, than he has already attained to; or that he cannot be content with a moderate power: but because he cannot assure the power and means to live well, which he hath present, without the acquisition of more."

*(Hobbes, Leviathan, Ch. XI, "A Restlesse Desire Of Power, In All Men"; PG #3207.)*

**[FLAG — Q4 LINKAGE POINT: see §Q4 below]**

**Evidence note:** The restlessness is not hedonistic escalation but structural insecurity. Hobbes is explicit: the cause is not the hope of greater pleasure but the inability to secure present power without acquiring more. This is a negative-spiral logic: each increment of power is insufficient to guarantee the security that would make further acquisition unnecessary. Death alone terminates the spiral. The logic is formally identical to what A&H call self-preservation driving limitless expansion (see Q4 note).

---

#### 1f. No Summum Bonum (Ch. XI, "What Is Here Meant By Manners")

> "To which end we are to consider, that the Felicity of this life, consisteth not in the repose of a mind satisfied. For there is no such Finis Ultimus, (utmost ayme,) nor Summum Bonum, (greatest good,) as is spoken of in the Books of the old Morall Philosophers. Nor can a man any more live, whose Desires are at an end, than he, whose Senses and Imaginations are at a stand. Felicity is a continuall progresse of the desire, from one object to another; the attaining of the former, being still but the way to the later."

*(Hobbes, Leviathan, Ch. XI, "What Is Here Meant By Manners"; PG #3207.)*

**Evidence note:** The explicit rejection of a highest good is the counterpart to the power-after-power argument. Aristotelian teleology (eudaimonia as resting point) is denied: felicity is not a terminal state but a perpetual forward motion. This removes any internal telos that would terminate self-authorization — there is no "enough." Combined with the power-after-power passage, this is the clearest statement of structurally limitless appetite in the empiricist tradition.

---

### Q2 — Stance toward Given Limits

#### 2a. State of nature as condition of war — limits are brute facts, not illegitimate (Ch. XIII)

> "And the life of man, solitary, poore, nasty, brutish, and short."

*(Hobbes, Leviathan, Ch. XIII; PG #3207.)*

> "…in the condition of meer Nature, (which is a condition of Warre of every man against every man,) upon any reasonable suspition, it is Voyd…"

*(Hobbes, Leviathan, Ch. XIV [continuation, "Warre of every man against every man" passage]; PG #3207.)*

**Evidence note:** For Hobbes, bodily finitude, vulnerability to violent death, and the scarcity of security are brute constitutive facts — not injustices to be overcome. The state of nature is not a call to transcend limits but the condition that makes the contract necessary. Given limits (mortality, mutual vulnerability) are treated as the unchangeable background against which political reason operates. They are constitutive, not targets of abolition.

---

#### 2b. Law of Nature: reason forbids self-destruction (Ch. XIV, "A Law Of Nature What")

> "A LAW OF NATURE, (Lex Naturalis,) is a Precept, or generall Rule, found out by Reason, by which a man is forbidden to do, that, which is destructive of his life, or taketh away the means of preserving the same; and to omit, that, by which he thinketh it may be best preserved."

*(Hobbes, Leviathan, Ch. XIV, "A Law Of Nature What"; PG #3207.)*

**Evidence note:** Reason's role is conservative — it forbids self-destruction. This is not reason legislating freedom but reason in service of animal preservation. Given limits (the fragility of the body, death as horizon) are the very precondition of the law of nature. They are accepted as constitutive.

---

#### 2c. Liberty and necessity consistent (Ch. XXI, "Liberty And Necessity Consistent")

> "Liberty and Necessity are Consistent: As in the water, that hath not only Liberty, but a Necessity of descending by the Channel: so likewise in the Actions which men voluntarily doe; which (because they proceed from their will) proceed from Liberty; and yet because every act of mans will, and every desire, and inclination proceedeth from some cause, which causes in a continuall chaine (whose first link in the hand of God the first of all causes) proceed from Necessity."

*(Hobbes, Leviathan, Ch. XXI, "Liberty And Necessity Consistent"; PG #3207.)*

**Evidence note (complication):** Hobbes is a hard necessitarian. Human action flows from a causal chain that ultimately derives from God. This is not voluntarist freedom; it is compatibilist. The "liberty" of the Hobbesian agent is entirely within a causal-mechanical universe — there is no space for the self to stand outside nature and negate given limits. This passage is a complication for any reading of Hobbes as endorsing an unconstrained will.

---

### Q3 — Anything Like 存在論的自由?

**Assessment: ABSENT in Hobbes. Bounded — and structurally so.**

The Hobbesian self is constituted by appetites that are themselves physical motions within a deterministic causal chain (Ch. XXI: "every desire, and inclination proceedeth from some cause"). Liberty is absence of *external* impediment, not self-constitution beyond given nature. There is no moment at which the Hobbesian subject stands outside all given determination and legislates itself. The rejection of Summum Bonum and the power-after-power restlessness *look* like limitlessness (and are the empiricist *seed* of the A&H engine), but this is structural insecurity, not ontological self-transcendence. The Hobbesian agent is answerable to its own survival-drive — which is precisely a given determination, not freedom from the given.

**[VERIFY: this absence reading — cross-check with secondary literature on Hobbesian voluntarism if needed before citing in thesis prose]**

---

### Q4 — Self-Preservation Lens: Hobbes and A&H

**Does Hobbes's self-preservation/appetite function as A&H's engine of enlightenment reason?**

**Answer: YES — and most directly of the three empiricists.**

The linkage is explicit and structural:

1. **A&H p.22 (Spinoza quote adopted as "true maxim"):** "Spinoza's proposition: 'the endeavor of preserving oneself is the first and only basis of virtue,' contains the true maxim of all Western civilization." A&H credit Spinoza but the Hobbesian drive precedes and grounds this: the right of nature (Ch. XIV) is precisely the liberty to do whatever "his own Judgement, and Reason, hee shall conceive to be the aptest means" to preserve his life. Hobbes makes self-preservation the *only* unconditional license — it is prior to all law, prior to contract. This is the empiricist seed that A&H's Spinoza formulation crystallizes.

2. **A&H p.23 (compulsive character):** "The exclusivity of logical laws stems from this obdurate adherence to function and ultimately from the compulsive character of self-preservation." Hobbes's power-after-power passage (Ch. XI) supplies the *mechanism*: the compulsion is not hedonic excess but structural insecurity. Each round of power-acquisition is insufficient to secure what the present round secured — the logic forces perpetual forward motion. This is A&H's "compulsive character" rendered in pre-capitalist political theory.

3. **A&H p.68 (constitutive principle):** "Self-preservation is the constitutive principle of science, the soul of the table of categories." In Hobbes, reason is already subordinated to self-preservation: the law of nature is found out by reason, but its content is entirely preservation-oriented (Ch. XIV: "a man is forbidden to do, that, which is destructive of his life"). Reason does not legislate freely; it is a detection instrument for survival-promoting actions.

4. **The limitlessness flag:** The power-after-power passage terminating "only in Death" (Ch. XI) is the empiricist seed of A&H's "control of internal and external nature has been made the absolute purpose of life" (p.24). For Hobbes, the drive to acquire does not terminate at a sufficient point — this is structurally identical to A&H's description of enlightenment as a project without a telos of completion. The difference: Hobbes grounds this in individual insecurity; A&H show it has become civilizational, social, and self-defeating.

5. **Self-preservation → self-destruction (A&H p.43, p.71):** Hobbes does *not* contain the dialectical reversal. For Hobbes, self-preservation succeeds (under the sovereign) — it does not destroy the self. The reversal is A&H's diagnosis of what Hobbes's logic *becomes* when socialized under capitalist apparatus. The Hobbesian logic is the seed; the dialectical inversion is the growth.

---

## PART II — JOHN LOCKE (*Second Treatise*, 1689; *Essay*, 1689)

---

### Q1 — Ground of Self-Authorization

#### 1a. State of perfect freedom — bounded by law of nature (§4)

> "…we must consider, what state all men are naturally in, and that is, a state of perfect freedom to order their actions, and dispose of their possessions and persons, as they think fit, within the bounds of the law of nature, without asking leave, or depending upon the will of any other man."

*(Locke, Second Treatise, §4; PG cached text.)*

**Evidence note:** The ground of Lockean self-authorization is freedom, but it is *immediately bounded*: "within the bounds of the law of nature." This is the crucial contrast with Hobbes. Hobbes's right of nature in the state of war is formally unlimited ("every man has a Right to every thing"); Locke's "perfect freedom" is structurally bounded by an obligation (the law of nature). The authorization is real but the form of its exercise is pre-constrained.

---

#### 1b. Property in one's own person (§27)

> "Though the earth, and all inferior creatures, be common to all men, yet every man has a property in his own person: this no body has any right to but himself. The labour of his body, and the work of his hands, we may say, are properly his. Whatsoever then he removes out of the state that nature hath provided, and left it in, he hath mixed his labour with, and joined to it something that is his own, and thereby makes it his property."

*(Locke, Second Treatise, §27; PG cached text.)*

**Evidence note:** Self-ownership is the ground of Lockean self-authorization. "Property in his own person" is the foundational claim: prior to any social contract or political order, the individual owns himself — body, labour, action. This is the empiricist doctrine of self-authorization at the political-economic level. Note that it is grounded in the physical fact of bodily agency (labour, removal from common state), not in rational autonomy.

---

#### 1c. Tabula rasa — epistemic self-constitution from experience (Essay II.i.2)

> "Let us then suppose the mind to be, as we say, white paper, void of all characters, without any ideas:—How comes it to be furnished? Whence comes it by that vast store which the busy and boundless fancy of man has painted on it with an almost endless variety? Whence has it all the MATERIALS of reason and knowledge? To this I answer, in one word, from EXPERIENCE. In that all our knowledge is founded; and from that it ultimately derives itself."

*(Locke, Essay Concerning Human Understanding, II.i.2, "All Ideas come from Sensation or Reflection"; PG #10615 cached text.)*

**Evidence note:** The tabula rasa doctrine is Locke's epistemic parallel to the political self-authorization thesis. If the mind begins as "white paper, void of all characters," then all mental content — including the materials of reason — is acquired, not innate. There is no pre-given rational structure that legislates in advance. The self is constituted through experience. This is the epistemic form of the empiricist self-authorization claim: the subject is not given a fixed nature by God or reason; it is formed from below by experience and sensation.

---

### Q2 — Stance toward Given Limits

#### 2a. Not a state of licence — law of nature as hard constraint (§6)

> "But though this be a state of liberty, yet it is not a state of licence: though man in that state have an uncontroulable liberty to dispose of his person or possessions, yet he has not liberty to destroy himself, or so much as any creature in his possession, but where some nobler use than its bare preservation calls for it. The state of nature has a law of nature to govern it, which obliges every one: and reason, which is that law, teaches all mankind, who will but consult it, that being all equal and independent, no one ought to harm another in his life, health, liberty, or possessions: for men being all the workmanship of one omnipotent, and infinitely wise maker; all the servants of one sovereign master, sent into the world by his order, and about his business; they are his property, whose workmanship they are, made to last during his, not one another's pleasure."

*(Locke, Second Treatise, §6; PG cached text.)*

**Evidence note (workmanship model):** The law of nature's authority derives from a theological ground: humans are God's workmanship ("the workmanship of one omnipotent, and infinitely wise maker"). This is the *theological* grounding of the limit. Given limits — including the prohibition on self-destruction and the duty to preserve others — are not merely prudential; they reflect the ontological fact that humans are property of their Maker. Lockean freedom is explicitly NOT a freedom to negate given limits; it operates within them as a structural precondition.

**[CONTRAST WITH HOBBES:]** Hobbes's law of nature also forbids self-destruction (Ch. XIV), but without the workmanship metaphysics — Hobbes grounds it in prudential self-interest. Locke grounds it in creatureliness. Both accept given limits as constitutive; the theological grounding makes Locke's acceptance structurally more robust.

---

#### 2b. Preservation duty extends to "the rest of mankind" (§6, continuation)

> "Every one, as he is bound to preserve himself, and not to quit his station wilfully, so by the like reason, when his own preservation comes not in competition, ought he, as much as he can, to preserve the rest of mankind, and may not, unless it be to do justice on an offender, take away, or impair the life, or what tends to the preservation of the life, the liberty, health, limb, or goods of another."

*(Locke, Second Treatise, §6; PG cached text.)*

**Evidence note:** Self-preservation is here not individualistic but relational: it generates a duty to preserve others when one's own preservation is not at stake. This is the inverse of Hobbes's war of all: for Locke, the same logic that grounds self-preservation extends to mutual preservation. Given limits (mortality, vulnerability) are constitutive not only of individual right but of inter-personal obligation.

---

### Q3 — Anything Like 存在論的自由?

**Assessment: ABSENT. More strongly bounded than Hobbes.**

Locke's "perfect freedom" (§4) is explicitly "within the bounds of the law of nature." The workmanship model (§6) further anchors the subject in a creaturely dependence: humans are God's property. The tabula rasa (Essay II.i.2) shows that the self is constituted through experience — but experience of *what is given* (sensory qualities of the world, operations of the mind on given materials). There is no moment at which the Lockean subject declares itself answerable to nothing given. The law of nature, God's ownership, and the obligation to preserve others all function as given constraints that the subject cannot legitimately transgress.

**[VERIFY: some contemporary Locke scholars (Simmons, Waldron) argue the workmanship model is itself in tension with the self-ownership thesis — flag if needed for thesis treatment]**

---

### Q4 — Self-Preservation Lens: Locke and A&H

**Does Locke's self-preservation function as A&H's engine?**

**Answer: PARTIALLY — but significantly attenuated by law-of-nature bounds.**

1. **A&H p.22 (Spinoza / maxim of Western civilization):** Locke's §27 (property in own person grounded in bodily labour) is the clearest expression of enlightenment self-authorization as *possession* of one's own powers. This feeds the A&H trajectory: if the body's labour is inalienably one's own, then the expansion of that labour's effects is the primary form of self-preservation in the economic register.

2. **BUT — the workmanship model is a structural brake:** Locke's theological grounding (§6) means that self-preservation is *not* the "first and only basis of virtue" in the Spinozist sense A&H deploy. God's prior ownership creates a duty not to destroy oneself or others. A&H's analysis concerns what Locke's logic *becomes when stripped of its theological scaffolding* — the self-ownership claim without the workmanship constraint. The dialectic of enlightenment is precisely the secularization that removes the brake.

3. **A&H p.68 (constitutive principle):** Locke's tabula rasa (Essay II.i) is relevant here but in a different register. If the mind is pure receptivity to experience, then the categories of knowledge are not given but constructed — and in A&H's reading, they are constructed in service of mastery and self-preservation. The tabula rasa is the epistemic form of A&H's claim that the "system's principles are those of self-preservation" (p.65): a mind with no innate structure acquires only what is useful.

4. **A&H p.43 (self-preservation destroys):** Locke does not contain this reversal. His self-preservation is bounded and mutual; it is not the limitless engine that destroys itself. The reversal remains A&H's diagnosis of the *unbound* trajectory.

---

## PART III — DAVID HUME (*Treatise*, 1739–40; *Enquiry*, 1748)

---

### Q1 — Ground of Self-Authorization

#### 1a. The self as bundle of perceptions — no persistent self-authorizing subject (Treatise 1.4.6)

> "…they are nothing but a bundle or collection of different perceptions, which succeed each other with an inconceivable rapidity, and are in a perpetual flux and movement. Our eyes cannot turn in their sockets without varying our perceptions. Our thought is still more variable than our sight; and all our other senses and faculties contribute to this change; nor is there any single power of the soul, which remains unalterably the same, perhaps for one moment. The mind is a kind of theatre, where several perceptions successively make their appearance; pass, re-pass, glide away, and mingle in an infinite variety of postures and situations. There is properly no simplicity in it at one time, nor identity in different; whatever natural propension we may have to imagine that simplicity and identity."

*(Hume, Treatise of Human Nature, 1.4.6 [Of Personal Identity]; PG #4705 cached text. Section confirmed: "SECT. VI." header at file index 551141, body begins immediately; bundle passage at file index 554692.)*

**Evidence note:** This is the most radical deflationary move in the empiricist tradition regarding the self. There is no persisting, identical self that authorizes — there are only successive perceptions. The "theatre" metaphor denies both simplicity (at any moment) and identity (across time). This undermines any notion of a robust self-authorizing subject: if there is no self, there is nothing to authorize. What authorizes, then? See Q1b: the passions and custom.

---

#### 1b. Reason is the slave of the passions (Treatise 2.3.3)

> "Reason is, and ought only to be the slave of the passions, and can never pretend to any other office than to serve and obey them."

*(Hume, Treatise of Human Nature, 2.3.3 [Of the Influencing Motives of the Will]; PG #4705 cached text. Section confirmed: "SECT. III. OF THE INFLUENCING MOTIVES OF THE WILL" header at file index 881375; passage at 886566.)*

> "A passion is an original existence, or, if you will, modification of existence, and contains not any representative quality, which renders it a copy of any other existence or modification. When I am angry, I am actually possest with the passion, and in that emotion have no more a reference to any other object, than when I am thirsty, or sick, or more than five foot high. It is impossible, therefore, that this passion can be opposed by, or be contradictory to truth and reason…"

*(Hume, Treatise 2.3.3; PG #4705.)*

> "It is not contrary to reason to prefer the destruction of the whole world to the scratching of my finger. It is not contrary to reason for me to chuse my total ruin, to prevent the least uneasiness of an Indian or person wholly unknown to me. It is as little contrary to reason to prefer even my own acknowledgeed lesser good to my greater, and have a more ardent affection for the former than the latter."

*(Hume, Treatise 2.3.3; PG #4705.)*

**Evidence note:** Three passages from the same section, escalating in radicality. (1) The programmatic claim: reason serves passions. (2) The ontological grounding: passions are "original existences," not representations — they cannot be logically contradicted. (3) The provocative illustrations: preferring world-destruction to a scratched finger is not contrary to reason. These illustrations are *not* Hume endorsing such preferences — they are demonstrations that reason alone cannot adjudicate between any preferences. The ground of self-authorization shifts entirely to passion/desire, with reason as the calculative servant.

---

#### 1c. Custom as the ground of action and inference (Enquiry §5)

> "Custom, then, is the great guide of human life. It is that principle alone which renders our experience useful to us, and makes us expect, for the future, a similar train of events with those which have appeared in the past. Without the influence of custom, we should be entirely ignorant of every matter of fact beyond what is immediately present to the memory and senses. We should never know how to adjust means to ends, or to employ our natural powers in the production of any effect."

*(Hume, Enquiry Concerning Human Understanding, §5; PG #9662 cached text.)*

**Evidence note:** Custom/habit is the positive answer to the question of what guides human life given that neither innate reason nor persisting self can do so. Custom is the accumulated residue of experience — but it operates *below* explicit rational justification. It is pre-reflective, sedimented, and constitutive. This is the Humean substitute for both Hobbesian appetite and Lockean law of nature: the given habit-structure of the agent is the ground of action.

---

### Q2 — Stance toward Given Limits

#### 2a. Uniformity of human actions — necessity as fact (Enquiry §8)

> "We must not, however, expect that this uniformity of human actions should be carried to such a length as that all men, in the same circumstances, will always act precisely in the same manner, without making any allowance for the diversity of characters, prejudices, and opinions. Such a uniformity in every particular, is found in no part of nature… Are the manners of men different in different ages and countries? We learn thence the great force of custom and education, which mould the human mind from its infancy and form it into a fixed and established character."

*(Hume, Enquiry §8; PG #9662 cached text.)*

**Evidence note:** Hume accepts the causal determination of character by custom and education as a brute fact. Human nature is not a fixed essence but it is not free-floating either — it is formed by habit, custom, and context. This is an acceptance of given formation: the self is not self-constituting from scratch but is shaped by its history and environment. Given limits of this kind are acknowledged as constitutive.

---

#### 2b. Compatibilist liberty — freedom within causal necessity (Enquiry §8)

> "By liberty, then, we can only mean _a power of acting or not acting, according to the determinations of the will;_ that is, if we choose to remain at rest, we may; if we choose to move, we also may. Now this hypothetical liberty is universally allowed to belong to every one who is not a prisoner and in chains."

*(Hume, Enquiry §8, §74; PG #9662 cached text. "Power of acting or not acting" passage at file index 180604.)*

**Evidence note:** Hume's compatibilist definition of liberty precisely accepts natural-causal necessity as the framework within which freedom operates. This is not the transcendence of given limits; it is the freedom to act *according to* one's will, which is itself determined by passion, custom, and causal history. Hume is among the least disposed of the three empiricists to endorse any form of 存在論的自由.

---

#### 2c. Death and dissolution — the self's annihilation (Treatise 1.4.6, adjacent)

> "…if all my perceptions were removed by death, and could I neither think, nor feel, nor see, nor love, nor hate after the dissolution of my body, I should be entirely annihilated, nor do I conceive what is farther requisite to make me a perfect non-entity."

*(Hume, Treatise 1.4.6; PG #4705 cached text. Passage at file index ~553800, immediately before the bundle passage.)*

**Evidence note:** Hume accepts bodily death as the literal end of the person. The dissolution of the body = the annihilation of the self (given that the self is a bundle of perceptions entirely dependent on physical processes). This is the starkest acceptance of given finitude in the empiricist tradition: death is not a problem to be overcome; it is the condition that makes the bundle-self intelligible as finite.

---

### Q3 — Anything Like 存在論的自由?

**Assessment: ABSENT — and more rigorously deflationary than either Hobbes or Locke.**

The bundle theory dissolves the self-authorizing subject entirely. There is no persistent "I" that could stand answerable to nothing given — because there is no "I" at all in the philosophically robust sense. The passions-as-ground mean that what authorizes action is pre-reflective affective states, not self-legislating reason. Custom as "great guide" means that the inherited formations of experience are constitutive, not freely chosen. Hume's compatibilism (Enquiry §8) closes off even the weak voluntarist reading.

**Complication:** The "destruction of the whole world" passage (Treatise 2.3.3) is sometimes read as approximating a radical preference-freedom — if reason cannot adjudicate any preference, is the self not answerable only to itself? But Hume's point is the opposite: the passions themselves are natural, caused occurrences; they are not acts of a free will. The apparent limitlessness of preference is an artifact of reason's incapacity to adjudicate, not evidence of ontological self-transcendence.

---

### Q4 — Self-Preservation Lens: Hume and A&H

**Does Hume's framework function as A&H's engine of enlightenment reason?**

**Answer: INDIRECTLY — as the epistemological dissolution of the self's countervailing structures.**

1. **A&H p.23 ("compulsive character of self-preservation"):** Hume does not centre self-preservation as Hobbes does. The passions are plural; self-preservation is not singled out as the master drive. However, Hume's reduction of reason to passion-service means that if the dominant passion *is* self-preservation (as Hobbes and Locke both suggest), then reason will serve that without remainder. The bundle theory removes the rational self that might otherwise resist or redirect the preservation drive.

2. **A&H p.65 ("system's principles are those of self-preservation; immaturity amounts to the inability to survive"):** Hume's account of custom and habit as the ground of action fits this: the "system" that A&H describe — in which experience is organized around mastery and survival — is exactly the kind of system that Humean habituation would produce if the dominant pressures are survival-oriented. The mind shaped by custom under scarcity and danger would become what A&H describe.

3. **A&H p.68 (self-preservation as soul of categories):** Hume's tabula-rasa epistemology (shared with Locke) supports this. If all categories derive from experience, and experience is shaped by the pressures of survival and power, then the categories *are* organized around self-preservation — not by philosophical choice but by the causal structure of how experience forms them.

4. **Bundle theory as dissolution of resistance:** A&H's analysis requires that the self be hollowed out by self-preservation — "self-preservation destroys the very thing which is to be preserved" (p.43). Hume's bundle theory anticipates this hollow self: if there was never a robust persisting subject in the first place, then the self-undoing that A&H diagnose is already philosophically encoded in empiricist psychology.

5. **Limitation:** Hume's caution and anti-enthusiasm (expressed throughout the Enquiry) is a structural complication. His acceptance of custom and limitation, his skepticism of metaphysical pretension, and his naturalism are all *conservative* features — they resist the projective drive A&H diagnose. Hume is the empiricist least susceptible to the hubris of the enlightenment project. The engine A&H describe is more clearly Hobbesian than Humean.

**[VERIFY: Some interpreters (Ainslie, Stroud) read Hume's bundle theory as a kind of liberating dissolution of fixed identity — worth checking if this reading is relevant to the 存在論的自由 thread before final thesis draft]**

---

## Synthesis Table

*Filled ONLY from verbatim passages above. Gaps marked [VERIFY/not found].*

| Author | Ground of self-authorization | Accepts given limits? | Yields 存在論的自由? | Self-preservation = engine? (per A&H) |
|--------|-----------------------------|-----------------------|--------------------|---------------------------------------|
| **Hobbes** | Right of nature = liberty to use one's own power for self-preservation (Ch. XIV); will = last appetite (Ch. VI); reason is instrumental only | YES — constitutively: law of nature forbids self-destruction (Ch. XIV); "life is solitary, poor, nasty, brutish and short" taken as brute fact; liberty-and-necessity compatible (Ch. XXI) | NO — liberty is absence of external impediment, not self-legislation; deterministic causal chain (Ch. XXI); power-after-power is structural insecurity, not ontological transcendence | YES — most directly: "power after power, ceaseth onely in Death" (Ch. XI) = structural limitlessness ↔ A&H p.22–23 (Spinoza maxim + compulsive character); Ch. XIV right of nature = unconditional license grounding A&H p.68 |
| **Locke** | Self-ownership / "property in his own person" (§27); "perfect freedom" within law of nature (§4); tabula rasa — mind formed from experience (Essay II.i.2) | YES — strongly: "not a state of licence" (§6); workmanship model grounds prohibition on self-destruction; duty to preserve others (§6); theological scaffolding is structural brake | NO — "perfect freedom" is explicitly "within the bounds of the law of nature" (§4); creaturely dependence on God (§6) | PARTIAL — self-ownership (§27) feeds A&H's possession-expansion logic; but theological brake (workmanship model, §6) attenuates engine-function; A&H's engine requires the theological scaffolding to be stripped away |
| **Hume** | Passion as "original existence" (Treatise 2.3.3); reason its slave; custom as "great guide" (Enquiry §5); no persistent self (bundle theory, Treatise 1.4.6) | YES — causal determination of character by custom/education accepted (Enquiry §8); compatibilist liberty = acting per will, not beyond causal necessity (§8); bodily death = annihilation, accepted (Treatise 1.4.6) | NO — bundle theory dissolves self; compatibilism closes voluntarist exit; "world-destruction" preference is not ontological self-transcendence but demonstration of reason's incapacity | INDIRECT — reason-as-slave means if dominant passion is self-preservation, reason serves it unrestrainedly; bundle theory pre-figures hollow self (A&H p.43); but Hume's conservatism/naturalism is anti-hubristic, resisting projective drive A&H diagnose |

---

## A&H Cross-Reference Summary

| A&H page | Passage (summary) | Most relevant empiricist anchor |
|----------|--------------------|--------------------------------|
| p.22 | Spinoza self-preservation = "true maxim of Western civilization"; anything outside self-preservation's functional context = myth | Hobbes Ch. XIV (right of nature = liberty for self-preservation, unconditionally) |
| p.23 | "Compulsive character of self-preservation" grounds logical formalism | Hobbes Ch. XI (power-after-power, structural insecurity, "ceaseth onely in Death") |
| p.24 | "Control of internal and external nature has been made the absolute purpose of life" | Hobbes Ch. XI (no Summum Bonum; felicity = perpetual progress of desire) |
| p.65 | "System's principles are those of self-preservation; immaturity = inability to survive" | Locke Essay II.i.2 (tabula rasa — categories formed from survival-shaped experience); Hume Enquiry §5 (custom formed by dominant pressures) |
| p.68 | "Self-preservation is the constitutive principle of science, the soul of the table of categories" | Hobbes Ch. XIV (reason as instrument of self-preservation); Locke Essay II.i.2 (experience as sole source of all ideas); Hume 2.3.3 (reason as slave of passions) |
| p.43 | "Self-preservation destroys the very thing which is to be preserved" | No direct empiricist anchor — this is the *reversal* that the empiricists do not contain. Pre-figured structurally by Hume's bundle theory (no robust self to preserve) but not stated by any empiricist. Gap flagged. |
| p.71 | "Self-preservation… no longer distinguishable from self-destruction" | No direct empiricist anchor — structural: all three empiricists accept given limits and do not contain the self-undermining logic. Gap: the reversal is A&H's diagnosis of what the logic *becomes*, not what any empiricist asserts. |

---

*Dossier compiled 2026-06-05 by Claude Code (claude-sonnet-4-6). All primary passages verbatim from Project Gutenberg OA cached files unless marked [paraphrase]. No paraphrases used. NLM attempted (A-Sources notebook `c68ca15e`); auth expired; abandoned after one attempt; cascade fell to OA cache (Tier 4). Status: ai-draft. Do not promote without human review.*
