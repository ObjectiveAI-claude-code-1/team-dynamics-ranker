# Team Dynamics Ranker: A Philosophy of Founder Evaluation

## Introduction

The team-dynamics-ranker function is designed to evaluate and rank founder groups based on their team composition and interpersonal dynamics. This is not merely a mechanical scoring exercise—it is an attempt to quantify one of the most profound and consequential aspects of startup success: the alchemy of human collaboration under extreme conditions.

Venture capitalists often say they invest in teams, not ideas. Ideas pivot; markets shift; technologies become obsolete. What remains constant is the people who must navigate these changes together. The team-dynamics-ranker embodies this philosophy, providing a systematic framework for evaluating the qualities that make founder groups resilient, effective, and likely to endure.

## Purpose and Philosophy

### The Core Question

At its heart, this function answers a deceptively simple question: **Which of these founder groups has the healthiest composition and dynamics for building a successful startup?**

This question requires unpacking several embedded assumptions:

1. **Composition matters**: The individual attributes of founders—their skills, backgrounds, and commitments—combine in non-linear ways to determine team effectiveness.

2. **Dynamics matter**: How founders relate to each other—their equity splits, geographic proximity, and implicit power structures—often predict outcomes more reliably than raw talent.

3. **Health is measurable**: While human relationships resist precise quantification, certain patterns reliably predict success or failure, and these patterns can be identified and weighted.

### Why Teams Fail

To understand what makes a great team, we must first understand why teams fail:

- **Skill gaps**: A team of all engineers cannot sell. A team of all salespeople cannot build. A team of domain experts without operators cannot execute.

- **Commitment asymmetry**: When some founders are "all in" while others hedge their bets, resentment festers and decision-making fractures.

- **Equity dysfunction**: Wildly unequal splits often mask power imbalances that will explode under stress. The founder with 5% will eventually ask why they're working as hard as the one with 60%.

- **Geographic fragmentation**: Remote-first works for scaled companies with established culture. For pre-product startups iterating at breakneck speed, physical proximity accelerates everything that matters.

- **Role confusion**: When three co-founders all see themselves as "the visionary CEO," conflict is inevitable. Clear differentiation enables parallel execution.

The team-dynamics-ranker is designed to surface these failure patterns early, before they become fatal.

## Input Structure and Interpretation

### The Founder Object

Each founder is represented by a structured object containing both hard facts and soft signals:

**Hard Facts (Required Fields)**:
- `name`: Identity anchor for the individual
- `role`: Their declared function within the team (CEO, CTO, etc.)
- `percent_equity`: Their ownership stake, a proxy for perceived value and commitment
- `technical_founder`: Boolean indicating engineering/product capability
- `in_school`: Boolean indicating part-time availability
- `commit_exclusively`: Boolean indicating full commitment

**Soft Signals (Optional but Revealing)**:
- `age`: Experience and energy trade-offs
- `gender`: Diversity as cognitive diversity proxy
- `city`: Geographic clustering and ecosystem access
- `education`: Credential signals (though often overweighted)
- `work_history`: Evidence of prior collaboration and domain expertise
- `hacked_system`: Creative problem-solving and resourcefulness
- `impressive_thing`: Peak achievement signal
- `built_things`: Evidence of shipping capability
- `accolades`: External validation

### Reading Between the Lines

The true skill in evaluating founder groups lies not in summing scores but in reading between the lines:

- A Stanford CS degree means something different for a 22-year-old building a developer tool than for a 45-year-old pivoting from finance.

- "CTO" on a two-person team where both have technical backgrounds signals role confusion, not complementarity.

- 40%/40%/20% equity split tells a story of two equals and one junior partner—is that structure intentional and healthy, or a compromise that will breed resentment?

## Evaluation Dimensions

### 1. Skill Complementarity

**What We're Evaluating**: Coverage of the three fundamental startup functions—building, selling, and domain expertise.

**The Philosophy**: Startups need to build products, sell them, and understand the problem space deeply. Most successful founding teams cover at least two of these well and can hire for the third. Teams where all founders share the same skillset face a dangerous blind spot.

**Strong Signals**:
- Clear builder/seller differentiation (classic technical + business pairing)
- Domain expertise in at least one founder
- Complementary backgrounds that suggest cognitive diversity
- Evidence of prior shipping in different domains

**Concerning Patterns**:
- All founders with identical backgrounds (three ML researchers, four MBAs)
- No technical founder in a technical product company
- No commercial founder in a market with complex sales
- Skills that overlap without complementing

**The Nuance**: Skill complementarity must be evaluated relative to the implied business. Three PhD researchers might be perfectly composed for a deep tech company but disastrously composed for a consumer social app.

### 2. Equity Distribution Health

**What We're Evaluating**: Whether the equity split reflects mutual respect and realistic contribution expectations.

**The Philosophy**: Equity is frozen compensation—it embeds assumptions about relative value that will persist for years. Healthy equity distributions don't require perfect equality, but they must pass the "resentment test": will each founder feel fairly compensated for their contribution in three years?

**Strong Signals**:
- Roughly equal splits (50/50, 33/33/34, 40/40/20) suggest mutual respect
- Deviations that match clear experience/commitment differences
- Vesting schedules implied by startup stage
- Solo founders with 100% (clear decision-making authority)

**Concerning Patterns**:
- Very small stakes (single digits) for ostensible co-founders
- One founder with overwhelming majority (80%+) alongside peers
- Equity splits that don't match role descriptions
- Many founders with nearly identical stakes (suggests non-decision)

**The Nuance**: Context matters enormously. A 60/40 split where the 60% founder is a second-time entrepreneur bringing capital and the 40% founder is a first-time technical genius may be perfectly healthy. The same split between two recent graduates with identical experience screams dysfunction.

### 3. Commitment Alignment

**What We're Evaluating**: Whether all founders have the same level of skin in the game.

**The Philosophy**: Startups demand everything. When some founders are fully committed while others maintain fallback options, the asymmetry creates friction. The fully committed resent the hedgers; the hedgers may be making rational individual decisions but are poisoning team dynamics.

**Strong Signals**:
- All founders with `commit_exclusively: true`
- All founders with `in_school: false` (or all in school together)
- Evidence of burned bridges (quit jobs, moved cities)
- Work history showing they've previously gone "all in"

**Concerning Patterns**:
- Mixed commitment levels within the team
- In-school founders paired with full-time founders
- "Advisors" with founder equity but no commitment
- Part-time "co-founders" maintaining other jobs

**The Nuance**: All founders being in school together is different from some in school and some not. The former is a cohort with aligned constraints; the latter is a commitment mismatch.

### 4. Team Size Appropriateness

**What We're Evaluating**: Whether the number of founders matches the company's needs and stage.

**The Philosophy**: Two to three founders is the statistical sweet spot—enough perspectives to avoid blind spots, few enough to make fast decisions. Solo founders face loneliness and limited bandwidth. Four or more founders require exceptional coordination and often signal inability to make hard decisions about who belongs on the founding team.

**Strong Signals**:
- Two to three founders with clear role differentiation
- Solo founder with particularly strong background and support network
- Four founders where the fourth adds clearly differentiated value

**Concerning Patterns**:
- Five or more founders (too many cooks)
- Solo founder without exceptional justification
- Three founders without clear differentiation
- Team size that suggests "everyone we know" rather than deliberate selection

**The Nuance**: Team size must be evaluated relative to ambition. A complex hardware company might justify four founders across mechanical, electrical, software, and commercial domains. A simple SaaS play with four founders signals indecision.

### 5. Geographic Considerations

**What We're Evaluating**: Physical proximity and ecosystem access.

**The Philosophy**: Co-location accelerates everything in early-stage startups. The spontaneous conversation at the whiteboard, the shared meals during crunch time, the ambient awareness of each other's work—these cannot be replicated over Zoom. Additionally, being in a startup ecosystem provides access to talent, capital, and pattern recognition that matters.

**Strong Signals**:
- All founders in the same city
- Founders located in major startup ecosystems (SF, NYC, Seattle, Austin, Boston, London, etc.)
- Evidence of recent relocation to work together
- Overlapping location in work history

**Concerning Patterns**:
- Founders distributed across multiple cities
- Founders in locations without startup infrastructure
- International distribution without plans to consolidate
- "We'll figure out co-location later"

**The Nuance**: Remote-first can work at scale, but it's a handicap at the founding stage. The question is not whether remote work is possible but whether it's optimal for zero-to-one company building.

### 6. Prior Working Relationships

**What We're Evaluating**: Evidence that these specific humans have successfully collaborated before.

**The Philosophy**: Founder relationships are marriages with money. Evidence of prior collaboration—having worked at the same company, built projects together, survived conflict together—dramatically increases the probability of successful co-founder dynamics. Strangers who meet at a hackathon and decide to start a company are running a dangerous experiment.

**Strong Signals**:
- Overlapping work history at the same companies
- Shared projects or ventures mentioned in backgrounds
- Long-term relationships implied by shared education/location
- Evidence of having weathered professional challenges together

**Concerning Patterns**:
- No overlap in work history or background
- "Met at a co-founder dating event"
- Very recent introductions
- Only academic collaboration without professional context

**The Nuance**: Not all prior relationships are positive signals. Former colleagues at a toxic company might have survived together or might have imported dysfunction. The quality of the prior relationship matters as much as its existence.

## Holistic Evaluation

### The Integration Challenge

No single dimension determines team quality. A team with perfect skill complementarity but equity dysfunction will fail. A perfectly committed team without technical talent will build nothing. The function must integrate across dimensions while remaining sensitive to the relative importance of each factor.

### Hierarchy of Concerns

When evaluating trade-offs, this function prioritizes:

1. **Commitment alignment** (most fundamental—without commitment, nothing else matters)
2. **Skill complementarity** (can they build and sell?)
3. **Equity health** (will they stay together under stress?)
4. **Prior relationships** (do they know how to work together?)
5. **Geographic considerations** (can they execute at startup speed?)
6. **Team size** (is the structure appropriate?)

### Red Flags vs. Yellow Flags

Some signals should be disqualifying:
- No technical founder for a technical product
- Commitment levels that are fundamentally misaligned
- Equity distributions that are clearly exploitative

Other signals are concerning but not fatal:
- Geographic distribution (can be resolved)
- Larger than ideal team size (can be managed)
- No prior working relationship (can develop)

### The "Would You Work for This Team?" Test

Ultimately, the function must answer: if you were an early employee, would you bet your career on this team? Would you leave a stable job to join them? Would you trust them to be in the same foxhole during the inevitable hard times?

## Use Cases

### Primary Use Case: Batch Comparison

When evaluating multiple founder groups applying to a program, accelerator, or investment round, the function ranks them by team composition quality. This is not a filter for ideas—it's a filter for execution capability.

### Secondary Use Case: Team Health Check

Existing teams can be evaluated against the framework to identify potential areas of concern before they become crises.

### Tertiary Use Case: Team Formation Guidance

Individuals forming teams can use the framework to understand what gaps they need to fill and what structures to establish.

## Conclusion

The team-dynamics-ranker embodies a philosophy: that the quality of human collaboration is evaluable, that certain patterns predict success and failure, and that systematic analysis can surface insights that intuition alone might miss.

It is not a replacement for judgment—no function can capture the full complexity of human relationships. But it is a structured lens through which to view the most important factor in startup success: the people who will do the building.

The function selects the ONE team with the healthiest composition and dynamics because startup success requires excellence, not adequacy. In a competition for resources, talent, and market position, the team that executes best will win. And execution begins with composition.

When we evaluate founder groups, we are ultimately asking: which of these teams is most likely to survive the crucible of startup building, to navigate pivots and conflicts and near-death experiences, and to emerge on the other side having built something meaningful?

That is the question this function is designed to answer.
