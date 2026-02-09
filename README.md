# team-dynamics-ranker

A vector function that ranks founder groups by their team composition and dynamics. Returns a probability distribution where higher values indicate healthier team dynamics.

## Overview

This function evaluates founding teams across 14 dimensions organized into 6 categories to determine which team has the healthiest composition and dynamics for startup success.

## Input

```json
{
  "items": [
    [
      {
        "name": "Alice Chen",
        "role": "CEO",
        "percent_equity": 50,
        "technical_founder": false,
        "in_school": false,
        "commit_exclusively": true,
        "age": 32,
        "gender": "Female",
        "city": "San Francisco",
        "education": [{"institution": "Stanford GSB", "degree": "MBA", "field": "Business", "graduation_year": 2018}],
        "work_history": [{"company": "Stripe", "title": "Product Manager", "start_year": 2018, "end_year": 2023}],
        "built_things": "Led launch of Stripe Atlas expansion",
        "impressive_thing": "Grew product from $10M to $50M ARR"
      },
      {
        "name": "Bob Park",
        "role": "CTO",
        "percent_equity": 50,
        "technical_founder": true,
        "in_school": false,
        "commit_exclusively": true
      }
    ],
    [
      // Another founder group...
    ]
  ]
}
```

### Founder Object Fields

**Required:**
- `name` (string): Founder's name
- `role` (string): Declared role (CEO, CTO, COO, Co-founder, etc.)
- `percent_equity` (integer): Ownership stake (0-100)
- `technical_founder` (boolean): Whether founder has technical/engineering capability
- `in_school` (boolean): Whether founder is currently a student
- `commit_exclusively` (boolean): Whether founder is committed full-time

**Optional:**
- `age` (integer): Founder's age
- `gender` (string): Founder's gender
- `city` (string): Current city of residence
- `education` (array): Educational background
- `work_history` (array): Work experience
- `hacked_system` (string): Description of creative problem-solving
- `impressive_thing` (string): Most impressive prior achievement
- `built_things` (string): Description of things they've built
- `accolades` (string): Awards, recognition, external validation

## Output

Returns a probability distribution (array of numbers summing to ~1.0) where each value corresponds to a founder group in the input. Higher values indicate healthier team dynamics.

## Evaluation Dimensions

### 1. Commitment Alignment (Priority 1)
- **Exclusive Commitment**: All founders fully dedicated to the venture
- **School Status Alignment**: Consistent academic status (all in school or all out)

### 2. Skill Complementarity (Priority 2)
- **Technical Founder Presence**: At least one founder can build the product
- **Builder-Seller Differentiation**: Technical + business skills complement each other
- **Role Clarity**: Distinct, non-overlapping roles enable parallel execution
- **Background Diversity**: Cognitive diversity through varied backgrounds

### 3. Equity Distribution Health (Priority 3)
- **Equity Fairness**: Splits reflect mutual respect (roughly equal for peers)
- **Equity-Role Coherence**: Stakes match declared roles and contributions

### 4. Prior Relationships (Priority 4)
- **Prior Working Relationship**: Evidence of successful collaboration history

### 5. Geographic Considerations (Priority 5)
- **Co-location**: All founders in the same city
- **Ecosystem Access**: Located in major startup hubs

### 6. Team Size (Priority 6)
- **Appropriateness**: 2-3 founders is ideal; 4+ requires justification

### 7. Holistic Assessment
- **Execution Evidence**: Track record of building and shipping
- **Overall Team Health**: Coherent unit with no disqualifying red flags

## Strong Signals
- Clear role differentiation
- Healthy equity distribution
- Universal exclusive commitment
- Complementary skills (builder + seller)
- Co-location in startup ecosystems
- Prior working relationships

## Concerning Patterns
- All founders with same skillset
- Equity dysfunction (80%+ for one, single digits for others)
- Mixed commitment levels
- No technical founder
- Fragmented geography
- 5+ founders without clear differentiation

## Use Cases
- Accelerator/incubator application screening
- Investment due diligence
- Team formation guidance
- Co-founder compatibility assessment
