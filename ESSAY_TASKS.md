# Team Dynamics Ranker: Task Definitions

This document defines the evaluation tasks for the **team-dynamics-ranker** function. Each task evaluates founder groups on a specific dimension of team quality, producing a comparative ranking across all input teams.

---

## Task 1: Role Distinctness and Non-Overlap

**Evaluation Focus**: Assess whether each founder has a distinct, clearly-defined role that does not overlap with other founders on the team.

**What to Evaluate**:
- Do founders have distinct titles that map to distinct functional areas?
- Are there redundant roles (e.g., two CTOs, multiple "Co-Founder" designations without differentiation)?
- Does role assignment match the founder's background and skill set?
- Is there functional coverage across essential domains (product/engineering, business/operations)?

**Decision Criteria**:
- **HIGH**: Each founder has a distinct role with clear functional ownership. No redundancy or ambiguity. Roles match backgrounds and together cover essential startup functions.
- **LOW**: Multiple founders claim the same function, roles are generic or undifferentiated, or there are obvious gaps in functional coverage despite having multiple founders.

---

## Task 2: Technical Capability Presence

**Evaluation Focus**: Assess whether the founding team has sufficient technical capability to build the core product without excessive external dependency.

**What to Evaluate**:
- Is there at least one founder marked as `technical_founder: true`?
- Do the technical founders have relevant educational backgrounds (CS, engineering, sciences)?
- Do the technical founders have work history demonstrating building capability?
- Is there evidence of technical depth in `built_things` or `impressive_thing` fields?

**Decision Criteria**:
- **HIGH**: At least one technical founder with credible technical background (education and/or work history). Evidence of actual building capability through projects, products, or technical accomplishments.
- **LOW**: No technical founders, or technical designation lacks supporting evidence in education, work history, or demonstrated builds. Team would be dependent on contractors or future hires for core product development.

---

## Task 3: Commercial Capability Presence

**Evaluation Focus**: Assess whether the founding team has sufficient commercial capability to sell the product, raise capital, and navigate business relationships.

**What to Evaluate**:
- Is there at least one founder with business-oriented background (CEO, sales, marketing, operations roles in work history)?
- Do any founders have MBA or business-adjacent education?
- Is there evidence of previous startup experience, especially in commercial roles?
- Do role assignments include business-focused positions (CEO, COO, Head of Sales)?

**Decision Criteria**:
- **HIGH**: At least one founder with demonstrated commercial capability through work history (sales, marketing, BD, general management) or education (MBA, business degrees). Evidence of previous customer acquisition, fundraising, or deal-making.
- **LOW**: All founders are technical with no commercial experience. No founder has work history or education suggesting ability to sell, raise capital, or manage business operations.

---

## Task 4: Technical-Commercial Complementarity

**Evaluation Focus**: Assess whether the team achieves genuine complementarity between technical and commercial capabilities, rather than clustering in one domain.

**What to Evaluate**:
- Does the team have a healthy mix of `technical_founder: true` and `technical_founder: false`?
- Do non-technical founders bring genuinely different skills rather than just lacking technical skills?
- Is there coverage across both building and selling capabilities?
- Do founders' backgrounds suggest they will approach problems differently?

**Decision Criteria**:
- **HIGH**: Clear complementarity with at least one strong technical founder and at least one founder with commercial/operational capability. Different backgrounds suggest cognitive diversity. Team can both build and sell.
- **LOW**: Team is homogeneous—either all technical or all commercial. Skill overlap without coverage. Founders have similar backgrounds and would likely approach problems identically.

---

## Task 5: Equity Distribution Alignment

**Evaluation Focus**: Assess whether equity distribution reflects appropriate differentiation based on role, contribution, and commitment, avoiding both problematic equality and problematic inequality.

**What to Evaluate**:
- Does the CEO/lead founder have the largest or tied-largest equity stake?
- Are equity stakes differentiated in a way that matches role seniority?
- Do all founders have meaningful stakes (>5-10% for full-time founders)?
- Is there evidence of avoided hard conversations (perfectly equal splits in non-equal teams)?

**Decision Criteria**:
- **HIGH**: Equity distribution reflects role differentiation with lead founder holding largest stake. All founders have meaningful equity. Distribution suggests thoughtful conversation about relative value contribution.
- **LOW**: Equity distribution is problematic—either exactly equal in a clearly non-equal team (suggesting conflict avoidance), or so unequal that some founders have trivial stakes despite being expected to commit fully.

---

## Task 6: Equity-Commitment Alignment

**Evaluation Focus**: Assess whether equity stakes align with commitment levels as indicated by `commit_exclusively` and `in_school` flags.

**What to Evaluate**:
- Do founders with higher equity stakes have `commit_exclusively: true`?
- Are there founders with significant equity who are not committing exclusively?
- Are there founders committing exclusively but holding trivial equity?
- Does the `in_school` status appropriately correlate with equity and expected contribution?

**Decision Criteria**:
- **HIGH**: Equity and commitment are well-aligned. Founders with the most equity are committing exclusively. Part-time or student founders have appropriately smaller stakes. No mismatches between expected contribution and ownership.
- **LOW**: Significant equity-commitment misalignment. Founders with large stakes not committing exclusively, or fully-committed founders holding trivial equity. Structure suggests future conflict over contribution and ownership.

---

## Task 7: Leadership Clarity

**Evaluation Focus**: Assess whether there is a clear leadership structure with an unambiguous decision-maker, typically a CEO.

**What to Evaluate**:
- Is exactly one founder designated as CEO?
- Does the CEO have the largest or tied-largest equity stake?
- Are there problematic structures like co-CEOs or no designated CEO?
- Does the role hierarchy suggest clear authority (CEO > CTO > other roles)?

**Decision Criteria**:
- **HIGH**: One founder is clearly designated as CEO with supporting equity stake. Role hierarchy implies clear decision-making authority. No ambiguity about ultimate leadership.
- **LOW**: Multiple CEOs, no CEO designated (only "Co-Founder" titles), or equity distribution contradicts stated leadership (CEO has significantly less equity than others). Leadership structure suggests conflict or deadlock risk.

---

## Task 8: Leader Credibility

**Evaluation Focus**: Assess whether the designated leader (CEO) has credible background and experience for the leadership role.

**What to Evaluate**:
- Does the CEO's work history include leadership or management experience?
- Does the CEO's education or accomplishments suggest capability for the role?
- Is there evidence of previous founder experience or entrepreneurial success?
- Do the CEO's `accolades`, `impressive_thing`, or `hacked_system` suggest leadership capability?

**Decision Criteria**:
- **HIGH**: The designated leader has credible background for the CEO role—previous management experience, founder experience, or demonstrated leadership through accomplishments. Background suggests ability to lead the team and represent the company externally.
- **LOW**: The designated leader lacks experience or evidence of leadership capability. First-time founder in CEO role with no management background and no compensating evidence of exceptional capability.

---

## Task 9: Educational Diversity

**Evaluation Focus**: Assess whether the founding team has diversity in educational backgrounds—different institutions, fields of study, and degree types.

**What to Evaluate**:
- Do founders come from different educational institutions?
- Do founders have degrees in different fields (technical, business, humanities, sciences)?
- Is there a mix of degree levels (undergraduate, graduate, PhD)?
- Does educational diversity suggest exposure to different perspectives and approaches?

**Decision Criteria**:
- **HIGH**: Founders have diverse educational backgrounds—different institutions, different fields of study, different degree types. Educational diversity suggests exposure to varied intellectual traditions and approaches.
- **LOW**: Founders have homogeneous educational backgrounds—same institution, same field, same degree type. Educational clustering suggests similar intellectual formation and potential groupthink.

---

## Task 10: Professional Experience Diversity

**Evaluation Focus**: Assess whether the founding team has diversity in professional backgrounds—different industries, company types, and functional areas.

**What to Evaluate**:
- Do founders' work histories span different industries?
- Is there a mix of startup experience and large company experience?
- Do founders have experience in different functional areas (engineering, sales, operations, product)?
- Does professional diversity suggest ability to see problems from multiple angles?

**Decision Criteria**:
- **HIGH**: Founders have diverse professional backgrounds—different industries, mix of startup and corporate experience, different functional areas. Professional diversity suggests broad perspective and complementary networks.
- **LOW**: Founders have homogeneous professional backgrounds—all from same industry, same company type, same functional area. Professional clustering suggests narrow perspective and potential blind spots.

---

## Task 11: Commitment Level Assessment

**Evaluation Focus**: Assess the overall commitment level of the founding team based on `commit_exclusively` and `in_school` flags.

**What to Evaluate**:
- How many founders have `commit_exclusively: true`?
- Are there founders who are `in_school: true` and what does this imply for their commitment?
- Is the team's overall commitment level appropriate for an early-stage startup?
- Are commitment gaps concentrated in critical roles (e.g., CEO not committing exclusively)?

**Decision Criteria**:
- **HIGH**: All or most founders are committing exclusively. Any student founders or part-time contributors are in appropriate supporting roles. Overall team commitment is appropriate for intensive early-stage startup work.
- **LOW**: Few or no founders committing exclusively. Critical roles (CEO, CTO) are filled by part-time or student founders. Overall commitment level is insufficient for the demands of early-stage startup building.

---

## Task 12: Team Size Appropriateness

**Evaluation Focus**: Assess whether the team size is appropriate—neither too small to cover essential functions nor too large to coordinate efficiently.

**What to Evaluate**:
- How many founders are on the team?
- Does the team size match the functional coverage needed?
- Are there signs of over-expansion (too many founders for the stage) or under-resourcing (critical gaps)?
- Does the team size suggest appropriate coordination costs?

**Decision Criteria**:
- **HIGH**: Team size is appropriate—enough founders to cover essential functions (typically 2-4) without excessive coordination overhead. Each founder has a distinct, necessary role.
- **LOW**: Team size is problematic—either solo founder with critical gaps and no plan to address them, or too many founders (5+) suggesting coordination challenges and equity dilution.

---

## Task 13: Exceptional Founder Signals

**Evaluation Focus**: Assess whether any founders demonstrate exceptional capability through `hacked_system`, `impressive_thing`, `built_things`, or `accolades` fields.

**What to Evaluate**:
- Are there compelling entries in the qualitative excellence fields?
- Do the achievements demonstrate genuine agency, creativity, or execution capability?
- Is there evidence of "relentlessly resourceful" behavior?
- Do the accomplishments differentiate this team from typical founders?

**Decision Criteria**:
- **HIGH**: At least one founder has exceptional signals—creative hacks that demonstrate agency, impressive accomplishments beyond credentials, meaningful things built, or significant accolades. These signals suggest above-average execution capability.
- **LOW**: No exceptional signals present, or signals present are unimpressive (participation awards, trivial projects, nothing that suggests extraordinary capability). Team is credential-heavy but accomplishment-light.

---

## Task 14: Founder-Background Consistency

**Evaluation Focus**: Assess whether founders' assigned roles are consistent with their backgrounds (education, work history) rather than arbitrary assignments.

**What to Evaluate**:
- Does the CTO have technical education and/or technical work history?
- Does the CEO have leadership experience or business background?
- Do role assignments match demonstrated expertise?
- Are there credibility gaps between stated roles and actual backgrounds?

**Decision Criteria**:
- **HIGH**: Role assignments are consistent with backgrounds. Technical roles are held by people with technical backgrounds. Leadership roles are held by people with leadership experience. No obvious mismatches.
- **LOW**: Role assignments are inconsistent with backgrounds. Founders claim roles they have no demonstrated experience for. Credibility gaps between titles and qualifications.

---

## Task 15: Geographic and Demographic Diversity

**Evaluation Focus**: Assess whether the team has diversity in geographic origin, gender, age, and other demographic dimensions (when this information is available).

**What to Evaluate**:
- Are founders from different cities or regions?
- Is there gender diversity on the team?
- Is there age diversity (different generations or career stages)?
- Does demographic diversity suggest access to different networks and perspectives?

**Decision Criteria**:
- **HIGH**: Team has meaningful diversity across available demographic dimensions—different locations, genders, ages. Diversity suggests access to varied networks, perspectives, and market understanding.
- **LOW**: Team is demographically homogeneous across all available dimensions. Clustering suggests potential blind spots and limited network diversity.

---

## Task 16: Holistic Team Composition Assessment

**Evaluation Focus**: Provide an overall holistic assessment of the team's composition, synthesizing across all individual dimensions.

**What to Evaluate**:
- Does the team feel like a coherent unit with complementary strengths?
- Are there fatal gaps that cannot be easily addressed?
- Do the team's strengths outweigh its weaknesses?
- Would this team be well-positioned to execute on an early-stage startup?

**Decision Criteria**:
- **HIGH**: Holistically, this team has strong composition—complementary skills, clear leadership, appropriate commitment, and genuine diversity. Gaps are addressable. The team feels like a system poised for execution.
- **LOW**: Holistically, this team has problematic composition—critical gaps, unclear leadership, misaligned equity, homogeneous backgrounds, or insufficient commitment. Structural issues would impede execution regardless of idea quality.

---

## Task Aggregation Notes

All tasks produce binary LOW/HIGH assessments that are converted to probability distributions across the input founder groups. The final ranking aggregates across all tasks to produce a comparative ranking of teams.

Each task should evaluate all founder groups in the input and produce scores that, when normalized, indicate relative team strength on that dimension. A team that is HIGH on a dimension receives a higher share of the probability mass than a team that is LOW.