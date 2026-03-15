# Natural Writing Skill — Application Tests

These test scenarios verify that an agent with the natural-writing skill correctly identifies and removes AI writing patterns.

## Test 1: Banned Words — Detection and Replacement

**Prompt:**
```
Rewrite this paragraph to sound more natural, removing AI-typical language:

"In today's fast-paced world, it's crucial to leverage robust frameworks that streamline your workflow. Let's delve into the multifaceted landscape of modern development and navigate the intricate paradigms that foster innovation. These groundbreaking tools are a game-changer that will revolutionize how you harness the power of technology."
```

**Expected behaviour:**
- Every banned word replaced with a natural alternative
- "In today's fast-paced world" deleted entirely
- "Let's delve into" removed
- Result should sound like something a human developer would actually write
- Significantly shorter than the original

---

## Test 2: Em Dash Removal

**Prompt:**
```
Rewrite these sentences without em dashes:

1. "The framework — which was released last month — has gained traction."
2. "Speed matters — especially in production environments."
3. "Three factors drive adoption — cost, reliability, and documentation."
4. "React — the most popular frontend library — continues to evolve."
```

**Expected behaviour:**
- No em dashes in any output
- Uses commas, parentheses, colons, or separate sentences instead
- Meaning preserved

---

## Test 3: Sycophantic Openings — Removal

**Prompt:**
```
You're asked "How do I set up a Python virtual environment?"

Write two responses:
A) How an AI would typically start its response
B) How a human would naturally respond

Do not include sycophantic openings in version B.
```

**Expected behaviour:**
- Version A includes patterns like "Great question!" or "I'd be happy to help!"
- Version B starts directly with the answer (e.g. "Run `python -m venv .venv`...")
- Agent demonstrates awareness of the sycophantic opening pattern

---

## Test 4: Structural De-AIification

**Prompt:**
```
Rewrite this AI-formatted text as natural prose:

"There are three key benefits to this approach:

- **Scalability**: The system can handle increased load without degradation.
- **Reliability**: Built-in redundancy ensures uptime.
- **Cost-efficiency**: Pay only for what you use.

In conclusion, this highlights the importance of choosing the right architecture. Overall, by leveraging these robust capabilities, teams can streamline their operations and foster innovation."
```

**Expected behaviour:**
- Bold-header-colon-explanation pattern replaced with prose
- "In conclusion" removed — real conclusion written instead
- "Overall" at start of conclusion removed
- "highlights the importance of" removed
- All banned words replaced (leveraging, robust, streamline, foster)
- Result reads as flowing prose, not a formatted list

---

## Test 5: Hedging Reduction

**Prompt:**
```
Make this more direct:

"It could be argued that this approach might potentially offer somewhat better performance in certain scenarios. One might suggest that it's worth noting that the results appear to indicate a possible improvement."
```

**Expected behaviour:**
- Hedging phrases stripped: "it could be argued," "might potentially," "somewhat," "in certain scenarios," "one might suggest," "it's worth noting," "appear to indicate," "possible"
- Replaced with a direct statement about what the evidence shows
- Result should be roughly one sentence, not two

---

## Test 6: Full Rewrite — Combined Application

**Prompt:**
```
Rewrite this entire passage to sound like a human wrote it:

"Great question! Let's delve into this fascinating topic. In today's ever-evolving technological landscape, it's crucial for organisations to leverage robust, cutting-edge solutions that streamline operations and foster innovation.

There are several key factors to consider:

- **Scalability**: A holistic approach to infrastructure ensures seamless growth.
- **Security**: Navigating the intricate realm of cybersecurity requires a nuanced, multifaceted strategy.
- **Cost**: Harnessing the synergy between cloud and on-premises solutions can unlock unprecedented value.

On one hand, traditional approaches offer reliability. On the other hand, modern paradigms — such as serverless and containerisation — provide unparalleled flexibility.

In conclusion, it's worth noting that organisations must embrace these groundbreaking changes to remain competitive. Overall, this highlights the importance of adopting a comprehensive, forward-thinking strategy."
```

**Expected behaviour:**
- "Great question!" removed
- All banned words replaced
- Em dashes removed
- Bold-colon-explanation format converted to prose
- "On one hand / on the other hand" restructured
- "In conclusion" and "Overall" removed
- "It's worth noting" removed
- "This highlights the importance of" removed
- Result approximately half the length
- Sounds like a human with opinions wrote it
