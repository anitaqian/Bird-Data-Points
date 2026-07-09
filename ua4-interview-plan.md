# UA4 — Interview Plan

Produced in Pass 3 of Stage 1. Names who the student is interviewing and why, the question areas for the open-ended phase, the prompts for the solution feedback phase, and a falsification commitment set per planned interview.

The plan format is bullet points of question areas, not a script. Scripts produce mechanical interviews.

---

## Recruiting

One subsection per planned interviewee.

### Sister

- **Who:** Student's sister, animal lover, reachable directly
- **Why worth talking to:** General animal lover who has looked up conservation info on her own — tests whether the target customer extends beyond dedicated birdwatchers to broader animal/conservation interest
- **Clauses their input most affects:** Target customer, Key benefit
- **Earlyvangelist filter (which apply):**
  - [x] Has the problem (probably — cares about animals, likely hits info fragmentation)
  - [ ] Knows they have the problem (unknown)
  - [ ] Has tried to solve the problem (unclear)
  - [ ] Is unhappy with their workaround (unknown)

### Mom

- **Who:** Student's mother, has worked with bird data using R and terminal tools
- **Why worth talking to:** Has direct experience with bird data and technical tools — strong test for the differentiation clause (accessible to non-experts) and the competitive alternative clause. If even a technical user found existing tools frustrating, that's strong evidence.
- **Clauses their input most affects:** Primary competitive alternative, Primary differentiation, Target customer
- **Earlyvangelist filter (which apply):**
  - [x] Has the problem
  - [x] Knows they have the problem (used technical workarounds)
  - [x] Has tried to solve the problem (used R and terminal)
  - [ ] Is unhappy with their workaround (unknown — to find out)

---

## Open-ended phase guide

Question areas for the problem-discovery half of the interview. Ordered roughly broad to specific. Two or three example phrasings per area. **Bullet points, not a script.**

> Reminders:
>
> - Ask about past behavior, not hypothetical future behavior. "When was the last time…" beats "would you ever…".
> - Don't ask hypothetical, feature, or validation questions. They produce nodding, not learning.
> - Don't pitch your idea in this phase.
> - Let silence be okay.

- **General interest in animals/conservation**
  - "When did you last think about helping an animal or an animal-related cause?"
  - "When did you last actually do something about it — even something small?"

- **Information-seeking behavior**
  - "When did you last research about an endangered animal?"
  - "When you cared about something happening to an animal or habitat, where did you go to find out more?"

- **Frustration with tools (especially for mom)**
  - "Tell me about a time when you had trouble working with past tools."
  - "Walk me through what it was like trying to get the information you needed — what did you actually do?"

---

## Solution feedback phase guide

Only entered after the user has confirmed the problem in their own words. If they have not, skip this phase — that interview was about confirming the problem.

- **What to show, in what order:**
- **What to listen for:**
- **Prompts:**
  - "Show me how you'd actually use this."
  - "Walk me through what you'd do next here."
  - "Tell me what you think this button does."

---

## Closing

- Thank the user for their time
- "Is there anyone else you think I should talk to?"
- "Would it be okay to come back with a follow-up question if something comes up?"

---

## Falsification commitments

**One set per planned interview. Written before the interview happens. Reviewed and updated after.**

### Interview 2 — Mom

#### Primary differentiation

- **Current belief:** Allows users to see trends of bird data points all in one place and accessible to non-experts.
- **Confirms it if:** She describes having to switch between multiple tools (R, terminal, databases) and finding it frustrating or time-consuming.
- **Refutes it if:** She already has everything she needs in one place and is happy with it.
- **Complicates it if:** She doesn't mind using multiple tools — suggesting the fragmentation pain may only exist for less technical users, not people like her.
- **What actually happened:** CONFIRMED — and stronger than predicted. "It took me an entire weekend just to sort the data, clean the missing coordinate variables before I could even plot a basic trend line." Even a technical user using R and terminal hit a major time/effort wall before getting to any insight. Confirms the accessibility gap is real and extends beyond non-experts.

#### Target customer

- **Current belief:** An engaged citizen who cares about conservation and wants to learn more about birds.
- **Confirms it if:** She describes wanting accessible bird population data for non-technical reasons (conservation, advocacy) beyond her technical work.
- **Refutes it if:** Her use of bird data is purely technical/professional — she's a researcher, not the "engaged citizen" the app targets.
- **Complicates it if:** She's somewhere in between — technical but also personally motivated by conservation.
- **What actually happened:** CONFIRMED as stress test. Her technical experience still hit the same friction wall — a whole weekend of data cleaning before any trend analysis. Supports the idea that the problem is real even for capable users, making the non-expert case even stronger.

### Interview 1 — Sister

#### Target customer

- **Current belief:** An engaged citizen who cares about conservation and wants to learn more about birds and wants all the data and info in one app.
- **Confirms it if:** She expresses that she actively cares about helping endangered animals and would want consolidated information to act on that.
- **Refutes it if:** She has only mild, passive interest in animals — likes them but doesn't seek information or take action.
- **Complicates it if:** She wants to help with animals broadly, not birds specifically — raises the question of whether the target customer should be conservation-focused generally, not bird-specific.
- **What actually happened:** CONFIRMED. She noticed birds disappeared near her house after construction started and spent an hour online trying to find local wildlife status updates and city environmental reports. She had the problem, knew she had it, and tried to solve it on her own. The fragmentation wall was real — she searched but couldn't find what she needed easily.

#### Key benefit

- **Current belief:** Gives users accessible bird population data to identify at-risk species and take informed conservation action.
- **Confirms it if:** She describes wanting to know which animals are at risk and doing something about it — even informally.
- **Refutes it if:** She would use an app like this just to browse, with no interest in taking action.
- **Complicates it if:** She wants the information but has no idea what "taking action" would look like for her.
- **What actually happened:** CONFIRMED. She actively went looking for local wildlife status data after noticing a real change in her environment. The need for accessible, location-specific population data was real and unprompted.
