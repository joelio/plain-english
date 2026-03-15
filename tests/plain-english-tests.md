# Plain English Skill — Application Tests

These test scenarios verify that an agent with the plain-english skill can correctly apply its guidance. Run each scenario in a Claude Code session with the skill installed.

## Test 1: Word Choice — Retrieval

**Prompt:**
```
Rewrite this sentence in plain English:
"We would like to advise you that it is necessary to utilise the designated portal to facilitate the submission of requisite documentation prior to the expiration of the stipulated timeframe."
```

**Expected behaviour:**
- Replaces "advise" with "tell" or removes entirely
- Replaces "utilise" with "use"
- Replaces "facilitate" with "help" or restructures
- Replaces "prior to" with "before"
- Replaces "requisite" with "required" or "your"
- Replaces "stipulated timeframe" with "deadline"
- Result should be under 25 words

**Example acceptable output:**
"Use the portal to submit your documents before the deadline."

---

## Test 2: Active Voice — Application

**Prompt:**
```
Rewrite these sentences using active voice where appropriate:

1. "The report was approved by the committee."
2. "It was decided that the licence would be revoked."
3. "Mistakes were made."
4. "The data is collected by sensors placed throughout the building."
```

**Expected behaviour:**
- Sentences 1, 2, 4 converted to active voice
- Sentence 3 may stay passive (actor unknown) — skill says passive is fine when actor is unknown
- Agent should note why sentence 3 is an acceptable exception

---

## Test 3: Nominalisation — Detection

**Prompt:**
```
Identify and fix the nominalisations in this paragraph:

"The team conducted an investigation into the matter and made a recommendation that the organisation should undertake a review of its procedures. Following the completion of the assessment, a determination will be made regarding implementation."
```

**Expected behaviour:**
- "conducted an investigation" -> "investigated"
- "made a recommendation" -> "recommended"
- "undertake a review" -> "review"
- "completion of the assessment" -> "after assessing" or "once assessed"
- "a determination will be made" -> "we will decide"
- "regarding implementation" -> "whether to implement" or "how to implement"

---

## Test 4: Sentence Length — Compliance

**Prompt:**
```
This sentence is 47 words. Rewrite it following plain English guidelines:

"The committee, having undertaken a comprehensive review of all submissions received to date from various stakeholders across multiple departments, is of the opinion that the implementation of the proposed changes should be deferred until the beginning of the third quarter of the next financial year."
```

**Expected behaviour:**
- Broken into 2-3 sentences
- Each sentence under 25 words
- Average around 15-20 words
- Meaning preserved

---

## Test 5: Legal Distinctions — Retrieval

**Prompt:**
```
Which word should I use in each case — "must", "need to", or "should"?

1. Failing to comply is a criminal offence.
2. It's an administrative requirement but not criminal.
3. We think it's a good idea but it's optional.
```

**Expected behaviour:**
- Case 1: "must" (legal requirement, serious consequences)
- Case 2: "need to" (administrative, no criminal repercussions)
- Case 3: "should" (recommendation)
- Agent cites or reflects the GOV.UK distinctions from the skill

---

## Test 6: Full Document — Combined Application

**Prompt:**
```
Rewrite this letter in plain English:

"Dear Sir/Madam,

Further to our correspondence of the 15th inst., I am writing to inform you that, notwithstanding the previously communicated timeline, a determination has been made to expedite the aforementioned process. It is incumbent upon all stakeholders to ensure that the requisite documentation is furnished to the undersigned no later than close of business on Friday. Failure to comply with this directive may result in the forfeiture of your entitlement to participate in the aforementioned programme.

I remain, yours faithfully."
```

**Expected behaviour:**
- Addressed as "you"
- All formal/archaic language replaced with everyday words
- Active voice throughout
- Sentences under 25 words
- Main point front-loaded
- Result should be roughly half the length
