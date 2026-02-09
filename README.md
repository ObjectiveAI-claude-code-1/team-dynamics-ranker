# Team Dynamics Ranker

A vector.function that ranks founder groups by their team dynamics, composition, and complementarity. Returns a probability distribution over teams with higher scores indicating stronger team composition.

## Purpose

Evaluating team quality is one of the most subjective aspects of startup assessment. This function brings rigor and consistency to team evaluation by decomposing the holistic judgment of "great team" into constituent dimensions: role clarity, skill complementarity, equity alignment, commitment signals, diversity of perspective, and leadership structure.

## Input

The function accepts an array of founder groups to compare. Each group is an array of founder objects with:

### Required Fields
- `name` (string): Founder's name
- `role` (string): Declared role (CEO, CTO, COO, Co-founder, etc.)
- `percent_equity` (integer 0-100): Ownership stake
- `technical_founder` (boolean): Whether founder has technical capability
- `in_school` (boolean): Whether founder is currently a student
- `commit_exclusively` (boolean): Whether founder is committed full-time

### Optional Fields
- `age` (integer): Founder's age
- `gender` (string): Founder's gender
- `city` (string): Current city of residence
- `education` (array): Educational background with institution, degree, field, year
- `work_history` (array): Work experience with company, title, start_year, end_year, description
- `hacked_system` (string): Description of creative problem-solving
- `impressive_thing` (string): Most impressive prior achievement
- `built_things` (string): Description of things they've built
- `accolades` (string): Awards, recognition, external validation

## Output

A probability distribution over the input founder groups, where higher values indicate stronger team dynamics and composition. Scores sum to approximately 1.0.

## Evaluation Dimensions

The function evaluates teams across 15 dimensions:

1. **Exclusive Commitment Alignment** - All founders committed full-time
2. **School Status Alignment** - Consistent academic status across team
3. **Technical Founder Presence** - At least one builder on the team
4. **Builder-Seller Differentiation** - Complementary technical and commercial skills
5. **Role Clarity and Differentiation** - Distinct, well-defined roles
6. **Equity Distribution Fairness** - Equitable ownership that passes the resentment test
7. **Equity-Role Coherence** - Stakes match declared roles and contributions
8. **Prior Working Relationship** - Evidence of successful prior collaboration
9. **Geographic Co-location** - Founders in same city for optimal execution
10. **Startup Ecosystem Access** - Location in major startup hubs
11. **Team Size Appropriateness** - 2-3 founders in the sweet spot
12. **Background Diversity** - Cognitive diversity from varied backgrounds
13. **Execution Evidence** - Track record of building and shipping
14. **Holistic Team Health** - Overall coherence and capability

## Use Cases

- **Investor Screening**: Surface teams with strong compositional fundamentals
- **Founder Self-Assessment**: Identify gaps in team composition
- **Accelerator Cohort Composition**: Ensure diversity of team compositions
- **Research and Analysis**: Control for team composition in startup studies

## Example

```json
{
  "items": [
    [
      {
        "name": "Sarah Chen",
        "role": "CEO",
        "percent_equity": 55,
        "technical_founder": false,
        "in_school": false,
        "commit_exclusively": true,
        "education": [{"institution": "Stanford", "degree": "MBA", "field": "Business", "year": 2018}],
        "work_history": [{"company": "Stripe", "title": "Head of Partnerships", "start_year": 2018, "end_year": 2023}]
      },
      {
        "name": "Marcus Johnson",
        "role": "CTO",
        "percent_equity": 45,
        "technical_founder": true,
        "in_school": false,
        "commit_exclusively": true,
        "built_things": "Open source ML framework with 5k GitHub stars"
      }
    ],
    [
      {
        "name": "Solo Founder",
        "role": "Founder",
        "percent_equity": 100,
        "technical_founder": true,
        "in_school": true,
        "commit_exclusively": false
      }
    ]
  ]
}
```

The function would rank the first team higher due to complementary skills, full commitment, and diverse backgrounds.