# Team Dynamics Ranker: Task Definitions

This document defines the evaluation tasks that comprise the team-dynamics-ranker function. Each task corresponds to a specific dimension of team composition and dynamics evaluation, as outlined in ESSAY.md. Tasks are ordered by priority according to the Hierarchy of Concerns.

---

## Task 1: Exclusive Commitment Alignment

**Dimension**: Commitment Alignment (Priority 1)

**Purpose**: Evaluate whether all founders have committed exclusively to the venture, indicating aligned skin in the game.

**Evaluation Criteria**:
- Check the `commit_exclusively` field for all founders in the group
- All founders with `commit_exclusively: true` indicates strong alignment
- Mixed commitment levels (some true, some false) indicate concerning asymmetry
- Consider that commitment asymmetry breeds resentment and fractures decision-making

**Strong Signals (HIGH)**:
- All founders have `commit_exclusively: true`
- Evidence of burned bridges in work history (quit stable jobs)
- Relocations to work together

**Concerning Signals (LOW)**:
- Mixed `commit_exclusively` values within the team
- Founders maintaining other jobs or commitments
- "Advisors" with founder equity but no exclusive commitment

**Binary Choice**: LOW (mixed or absent exclusive commitment) vs HIGH (universal exclusive commitment)

---

## Task 2: School Status Alignment

**Dimension**: Commitment Alignment (Priority 1)

**Purpose**: Evaluate whether founders have aligned academic status, as mixed school/non-school teams face structural friction.

**Evaluation Criteria**:
- Check the `in_school` field for all founders
- All founders in school together = aligned cohort (acceptable)
- All founders not in school = full-time alignment (ideal)
- Mixed in_school status = commitment mismatch (concerning)

**Strong Signals (HIGH)**:
- All founders have `in_school: false` (full-time availability)
- All founders have `in_school: true` (cohort with aligned constraints)
- Consistent academic status across the team

**Concerning Signals (LOW)**:
- Some founders in school, others not
- Part-time students paired with full-time founders
- School commitments that will compete with startup demands

**Binary Choice**: LOW (mixed school status) vs HIGH (aligned school status—all in or all out)

---

## Task 3: Technical Founder Presence

**Dimension**: Skill Complementarity (Priority 2)

**Purpose**: Evaluate whether the team has at least one technical founder who can build the product.

**Evaluation Criteria**:
- Check the `technical_founder` field across the team
- At least one `technical_founder: true` is essential for most startups
- Multiple technical founders may be appropriate for deep-tech plays
- Zero technical founders is a critical gap for technology companies

**Strong Signals (HIGH)**:
- At least one founder with `technical_founder: true`
- Technical founder holds meaningful equity stake
- Technical capability evident from work history or built_things

**Concerning Signals (LOW)**:
- No founder with `technical_founder: true`
- All founders are non-technical (all business backgrounds)
- Outsourced technical capacity with founder equity

**Binary Choice**: LOW (no technical founder) vs HIGH (technical founder present)

---

## Task 4: Builder-Seller Differentiation

**Dimension**: Skill Complementarity (Priority 2)

**Purpose**: Evaluate whether the team has clear role differentiation between building (product/engineering) and selling (business/commercial) functions.

**Evaluation Criteria**:
- Examine roles, technical_founder flags, and work history for skill signals
- Classic pairing: technical founder + business/commercial founder
- Look for evidence of complementary rather than overlapping skills
- Consider whether the team can both build AND sell

**Strong Signals (HIGH)**:
- Clear technical + business pairing (e.g., CTO + CEO with sales background)
- Roles that indicate complementary functions (not all "Co-founder" or all "CEO")
- Work history showing different domain expertise
- Evidence of prior shipping AND prior selling

**Concerning Signals (LOW)**:
- All founders with identical backgrounds (three engineers, four MBAs)
- Roles that overlap without complementing (two CTOs, three "visionaries")
- No commercial/business founder in a complex sales environment
- Skills that duplicate rather than complete each other

**Binary Choice**: LOW (poor differentiation or skill gaps) vs HIGH (clear builder-seller complementarity)

---

## Task 5: Role Clarity and Differentiation

**Dimension**: Skill Complementarity (Priority 2)

**Purpose**: Evaluate whether founders have distinct, clearly defined roles that enable parallel execution.

**Evaluation Criteria**:
- Examine the `role` field for each founder
- Look for distinct functional roles (CEO, CTO, COO, CPO, etc.)
- Watch for role confusion signals (multiple CEOs, vague titles)
- Consider whether roles match founder backgrounds

**Strong Signals (HIGH)**:
- Distinct roles across founders (CEO + CTO + COO pattern)
- Roles that match technical_founder status and work history
- Clear division of responsibilities evident from role titles
- Solo founder with clear singular leadership (100% equity)

**Concerning Signals (LOW)**:
- Multiple founders with same or similar roles
- Vague roles like "Co-founder" without functional specification
- Role titles that don't match evident backgrounds
- All founders claiming CEO or "visionary" status

**Binary Choice**: LOW (role confusion or overlap) vs HIGH (clear role differentiation)

---

## Task 6: Equity Distribution Fairness

**Dimension**: Equity Distribution Health (Priority 3)

**Purpose**: Evaluate whether the equity split reflects mutual respect and will pass the "resentment test" over time.

**Evaluation Criteria**:
- Examine `percent_equity` across all founders
- Roughly equal splits (50/50, 33/33/34, 40/40/20) suggest mutual respect
- Very small stakes for ostensible co-founders (single digits) are concerning
- Solo founders with 100% is healthy (clear authority)
- Equity should roughly correspond to role seniority and commitment

**Strong Signals (HIGH)**:
- Roughly equal splits among co-founders (within 20% of each other)
- Deviations that match clear experience/role differences
- Solo founder with 100% (clear decision-making authority)
- No founder with less than 10% unless clearly an advisor/minor role

**Concerning Signals (LOW)**:
- One founder with 80%+ while peers have minimal stakes
- Co-founders with single-digit equity (suggests exploitation or miscalibration)
- Equity splits that contradict role descriptions
- Very equal splits among many founders (suggests non-decision/indecision)

**Binary Choice**: LOW (concerning equity distribution) vs HIGH (healthy equity distribution)

---

## Task 7: Equity-Role Coherence

**Dimension**: Equity Distribution Health (Priority 3)

**Purpose**: Evaluate whether equity stakes are coherent with declared roles and implied contributions.

**Evaluation Criteria**:
- Compare `percent_equity` against `role` and other signals
- CEO typically should have meaningful stake if leading
- Technical founders should have equity reflecting their building contribution
- Equity should tell a coherent story about relative value

**Strong Signals (HIGH)**:
- Lead role (CEO) corresponds with meaningful equity stake
- Technical founders have equity proportional to building responsibility
- Equity distribution tells a coherent story matching roles
- No obvious mismatches between title and stake

**Concerning Signals (LOW)**:
- CEO with tiny equity stake (who really leads?)
- Technical founder with minimal equity (will they stay?)
- Equity splits that contradict the role structure
- "Advisor" equity levels for people with "Founder" titles

**Binary Choice**: LOW (equity-role mismatch) vs HIGH (equity-role coherence)

---

## Task 8: Prior Working Relationship Evidence

**Dimension**: Prior Relationships (Priority 4)

**Purpose**: Evaluate whether founders have evidence of successful prior collaboration.

**Evaluation Criteria**:
- Examine `work_history` for overlapping companies or time periods
- Look for shared education institutions or locations
- Consider `built_things` that might reference shared projects
- Founder relationships are marriages with money—prior collaboration reduces risk

**Strong Signals (HIGH)**:
- Overlapping companies in work_history
- Shared educational institutions at same time periods
- References to joint projects in built_things or other fields
- Long-term geographic proximity suggesting established relationship
- Evidence of having weathered professional challenges together

**Concerning Signals (LOW)**:
- No overlap in work_history or educational background
- Founders from completely different industries/locations
- No evidence of prior collaboration
- Very recent relationship (startup-dating pattern)

**Binary Choice**: LOW (no prior relationship evidence) vs HIGH (clear prior relationship signals)

---

## Task 9: Geographic Co-location

**Dimension**: Geographic Considerations (Priority 5)

**Purpose**: Evaluate whether founders are co-located for optimal early-stage execution.

**Evaluation Criteria**:
- Examine `city` field for all founders
- All founders in same city = ideal co-location
- Founders distributed across cities = execution friction
- Consider proximity even if not same city (adjacent metros)

**Strong Signals (HIGH)**:
- All founders in the same city
- All founders in same metropolitan area
- Evidence of relocation to work together (city matches recent work_history change)
- Solo founder (co-location not applicable)

**Concerning Signals (LOW)**:
- Founders distributed across multiple cities
- International distribution across time zones
- No evidence of plans to consolidate
- Major cities with poor connectivity (e.g., SF + Singapore)

**Binary Choice**: LOW (distributed team) vs HIGH (co-located team)

---

## Task 10: Startup Ecosystem Access

**Dimension**: Geographic Considerations (Priority 5)

**Purpose**: Evaluate whether founders are located in startup ecosystems with access to talent, capital, and pattern recognition.

**Evaluation Criteria**:
- Examine `city` for ecosystem signals
- Major startup hubs: San Francisco, New York, Seattle, Austin, Boston, Los Angeles, London, Singapore, Berlin, Tel Aviv, etc.
- Consider quality of local startup infrastructure
- Ecosystem access provides advantages but is not essential

**Strong Signals (HIGH)**:
- Founders located in major startup ecosystems
- Access to relevant industry clusters (fintech in NYC, biotech in Boston)
- Cities with strong venture capital presence
- Hubs with relevant talent pools

**Concerning Signals (LOW)**:
- Founders in cities without startup infrastructure
- Locations far from relevant industry ecosystems
- No access to startup networks or capital
- Isolation from pattern recognition and mentorship

**Binary Choice**: LOW (poor ecosystem access) vs HIGH (strong ecosystem access)

---

## Task 11: Team Size Appropriateness

**Dimension**: Team Size (Priority 6)

**Purpose**: Evaluate whether the number of founders is appropriate for effective startup execution.

**Evaluation Criteria**:
- Count the number of founders in the group
- 2-3 founders = statistical sweet spot
- Solo founder = viable but higher risk (loneliness, limited bandwidth)
- 4+ founders = coordination overhead, possible inability to make hard decisions

**Strong Signals (HIGH)**:
- 2-3 founders with clear role differentiation
- Solo founder with exceptional background (can be appropriate)
- 4 founders where fourth adds clearly differentiated value
- Team size matches venture complexity

**Concerning Signals (LOW)**:
- 5+ founders (too many decision-makers)
- Solo founder without exceptional justification
- 4+ founders without clear differentiation
- Team size suggesting "everyone we know" rather than deliberate selection

**Binary Choice**: LOW (inappropriate team size) vs HIGH (appropriate team size)

---

## Task 12: Background Diversity and Cognitive Diversity

**Dimension**: Skill Complementarity (Priority 2)

**Purpose**: Evaluate whether the team has diverse backgrounds that suggest cognitive diversity and complementary perspectives.

**Evaluation Criteria**:
- Examine `education`, `work_history`, `age`, and `gender` for diversity signals
- Different educational backgrounds suggest different thinking styles
- Varied work history indicates breadth of experience
- Age diversity can balance energy and experience
- Gender diversity often correlates with cognitive diversity

**Strong Signals (HIGH)**:
- Founders from different educational backgrounds (CS + MBA, engineering + design)
- Varied work history across industries or functions
- Mix of ages bringing different perspectives
- Gender diversity on the team
- Evidence of both technical and commercial experience

**Concerning Signals (LOW)**:
- All founders from identical backgrounds (same school, same company)
- Homogeneous work history (all consultants, all from same startup)
- No diversity in educational or professional backgrounds
- Echo chamber composition

**Binary Choice**: LOW (homogeneous backgrounds) vs HIGH (diverse backgrounds)

---

## Task 13: Execution Evidence

**Dimension**: Holistic Capability Assessment

**Purpose**: Evaluate whether founders have demonstrated ability to ship and execute.

**Evaluation Criteria**:
- Examine `built_things`, `impressive_thing`, `hacked_system`, and `work_history`
- Look for evidence of prior shipping (products launched, companies built)
- Consider creative problem-solving demonstrated in `hacked_system`
- Evaluate quality of prior execution from `impressive_thing`

**Strong Signals (HIGH)**:
- Multiple founders with evidence in `built_things`
- Impressive prior achievements in `impressive_thing`
- Creative problem-solving in `hacked_system`
- Work history showing progression and impact
- Evidence of having shipped real products to real users

**Concerning Signals (LOW)**:
- No evidence of prior building in any founder
- Empty or weak `built_things` across the team
- No impressive achievements to point to
- Work history suggesting observer rather than builder roles
- All credentials, no demonstrated execution

**Binary Choice**: LOW (limited execution evidence) vs HIGH (strong execution evidence)

---

## Task 14: Holistic Team Health Assessment

**Dimension**: Integration Across All Dimensions

**Purpose**: Provide an overall assessment of team composition and dynamics, integrating signals across all dimensions.

**Evaluation Criteria**:
- Consider the cumulative effect of all individual assessments
- Apply the "Would you work for this team?" test
- Look for patterns of strength or weakness across dimensions
- Consider whether red flags are offset by exceptional strengths
- Evaluate whether the team feels coherent and capable

**Strong Signals (HIGH)**:
- Consistent strength across multiple dimensions
- No disqualifying red flags (no technical founder, equity dysfunction, commitment mismatch)
- Team feels like a coherent unit with complementary capabilities
- Would confidently recommend joining this team
- Evidence suggests resilience under stress

**Concerning Signals (LOW)**:
- Multiple concerning patterns across dimensions
- Presence of any disqualifying red flags
- Team feels assembled from parts rather than unified
- Would hesitate to recommend joining
- Structural issues likely to surface under stress

**Binary Choice**: LOW (concerning overall team health) vs HIGH (strong overall team health)

---

## Task Summary

| # | Task Name | Dimension | Priority |
|---|-----------|-----------|----------|
| 1 | Exclusive Commitment Alignment | Commitment | 1 |
| 2 | School Status Alignment | Commitment | 1 |
| 3 | Technical Founder Presence | Skill Complementarity | 2 |
| 4 | Builder-Seller Differentiation | Skill Complementarity | 2 |
| 5 | Role Clarity and Differentiation | Skill Complementarity | 2 |
| 6 | Equity Distribution Fairness | Equity Health | 3 |
| 7 | Equity-Role Coherence | Equity Health | 3 |
| 8 | Prior Working Relationship Evidence | Prior Relationships | 4 |
| 9 | Geographic Co-location | Geography | 5 |
| 10 | Startup Ecosystem Access | Geography | 5 |
| 11 | Team Size Appropriateness | Team Size | 6 |
| 12 | Background Diversity | Skill Complementarity | 2 |
| 13 | Execution Evidence | Holistic Capability | — |
| 14 | Holistic Team Health Assessment | Integration | — |

---

## Implementation Notes

1. **Input Format**: Each task receives a founder group (array of founder objects) formatted as a readable text representation of the structured data.

2. **Binary Responses**: Each task outputs a binary LOW/HIGH assessment, where HIGH indicates the team scores well on that dimension.

3. **Score Aggregation**: Individual task scores are normalized to produce a probability distribution across founder groups, with higher aggregate scores indicating healthier team dynamics.

4. **Priority Weighting**: While all tasks contribute to the final ranking, the priority ordering reflects the relative importance of each dimension—commitment issues should weigh more heavily than geographic distribution.

5. **Red Flag Detection**: Tasks 1-3 and 6 are designed to surface potential disqualifying issues. A team failing on these dimensions faces structural challenges that are difficult to overcome.
