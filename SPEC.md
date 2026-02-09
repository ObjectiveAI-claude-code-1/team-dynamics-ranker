Create a vector function that ranks founder groups by their team composition and dynamics.

Input schema:
- type: object with 'items' property
- items: array of founder groups (each group is an array of founder objects)
- minItems: 2
- Each founder object has: name (string), age (integer), gender (string), city (string), role (string), percent_equity (integer), technical_founder (boolean), in_school (boolean), commit_exclusively (boolean), education (array), work_history (array), hacked_system (string), impressive_thing (string), built_things (string), accolades (string)
- Required fields per founder: name, role, percent_equity, technical_founder, in_school, commit_exclusively

This is a vector function that outputs a probability distribution across founder groups.

Evaluate team composition and dynamics by examining:
1. Skill complementarity - building, selling, domain expertise coverage
2. Equity distribution health - roughly equal splits suggest mutual respect, very small stakes are concerning
3. Commitment alignment - all commit_exclusively true, mixed in_school status
4. Team size appropriateness - 2-3 founders often ideal, 4+ requires justification
5. Geographic considerations - co-located teams execute better, startup ecosystem locations help
6. Prior working relationships - evidence from overlapping work history

Strong signals: Clear role differentiation, healthy equity distribution, universal commitment, complementary skills, co-location
Concerning patterns: All founders same skillset, equity dysfunction, mixed commitment, obvious gaps, fragmented geography

Select the ONE team with the healthiest composition and dynamics.