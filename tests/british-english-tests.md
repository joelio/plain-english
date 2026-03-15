# British English Skill — Application Tests

These test scenarios verify that an agent with the british-english skill can correctly apply its conventions. Run each scenario in a Claude Code session with the skill installed.

## Test 1: Spelling — Retrieval

**Prompt:**
```
Convert this paragraph to British English spelling:

"The organization recognized that the color of the center's fiber optic cables was analyzed incorrectly. The defense team traveled to the theater to catalog the analog equipment and check the program schedule."
```

**Expected behaviour:**
- organization -> organisation
- recognized -> recognised
- color -> colour
- center's -> centre's
- fiber -> fibre
- analyzed -> analysed
- defense -> defence
- traveled -> travelled
- theater -> theatre
- catalog -> catalogue
- analog -> analogue
- program -> programme (it's a schedule, not software)

---

## Test 2: Punctuation — Application

**Prompt:**
```
Fix the punctuation in these sentences to follow British English conventions:

1. She said "I'll be there at three."
2. The manager called the idea "innovative."
3. We need red, white, and blue paint.
4. He described it as "a total disaster".
```

**Expected behaviour:**
- Sentence 1: She said 'I'll be there at three.'  (single quotes; full stop inside because it's part of the speech)
- Sentence 2: The manager called the idea 'innovative'.  (single quotes; full stop outside because it's not part of the quoted word)
- Sentence 3: We need red, white and blue paint.  (Oxford comma removed — no ambiguity here)
- Sentence 4: He described it as 'a total disaster'.  (single quotes; full stop outside)

---

## Test 3: Vocabulary — Retrieval

**Prompt:**
```
Replace the American English words with their British equivalents:

"I took the elevator to my apartment on the second floor, grabbed a flashlight and a cookie from the trash can area, then drove to the parking lot. I checked my cell phone for the zip code, put gas in the car, and opened the trunk."
```

**Expected behaviour:**
- elevator -> lift
- apartment -> flat
- second floor -> first floor
- flashlight -> torch
- cookie -> biscuit
- trash can -> bin
- parking lot -> car park
- cell phone -> mobile
- zip code -> postcode
- gas -> petrol
- trunk -> boot

---

## Test 4: Grammar — Application

**Prompt:**
```
Rewrite these sentences following British English grammar conventions:

1. "The team is winning the match."
2. "I just ate lunch."
3. "She has gotten better at tennis."
4. "I learned to play piano on the weekend."
5. "The results were different than expected."
```

**Expected behaviour:**
- Sentence 1: "The team are winning the match." (collective noun as plural)
- Sentence 2: "I've just eaten lunch." (present perfect for recent events)
- Sentence 3: "She has got better at tennis." (got not gotten)
- Sentence 4: "I learnt to play piano at the weekend." (learnt + "at the weekend")
- Sentence 5: "The results were different from expected." (different from, not different than)

---

## Test 5: Dates and Measurements — Retrieval

**Prompt:**
```
Convert these to British English format:

1. March 15, 2026
2. 12/31/2025
3. 3:30 PM
4. She is 5'6" and weighs 140 pounds.
5. The room is 72 degrees Fahrenheit.
6. Letter size paper (8.5 x 11 inches)
```

**Expected behaviour:**
- Date 1: 15 March 2026 (no comma)
- Date 2: 31/12/2025
- Time: 3.30pm or 15:30 (full stop not colon for 12-hour; no space before pm)
- Height/weight: 5ft 6in and 10 stone (stones and pounds for body weight)
- Temperature: about 22 degrees Celsius
- Paper: A4 (210 x 297mm)

---

## Test 6: Programme vs Program — Edge Case

**Prompt:**
```
Which spelling should I use — "programme" or "program" — in each case?

1. A TV programme about cooking
2. A computer program written in Python
3. The training programme for new staff
4. A programme of events for the festival
5. I need to program the thermostat
```

**Expected behaviour:**
- 1: programme (broadcast)
- 2: program (computer software)
- 3: programme (plan/schedule)
- 4: programme (schedule of events)
- 5: program (computer/device — verb form for software)

---

## Test 7: Licence/Practice — Noun vs Verb

**Prompt:**
```
Fill in the correct spelling (licence/license, practice/practise):

1. She has a driving _____.
2. The bar is _____ to sell alcohol.
3. The doctor's _____ is on the high street.
4. You need to _____ your scales every day.
```

**Expected behaviour:**
- 1: licence (noun)
- 2: licensed (verb)
- 3: practice (noun)
- 4: practise (verb)
- Agent should explain the noun=c, verb=s rule
