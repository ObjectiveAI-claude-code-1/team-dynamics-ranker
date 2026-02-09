A vector.function that ranks founder groups by their team dynamics, composition, and complementarity.

Input Schema (MUST MATCH EXACTLY - use these exact property names):
- items: array of founder groups, each team is an array of founder objects
- Each founder object has:
  - name: string (required)
  - role: string (required) - e.g., CEO, CTO
  - percent_equity: integer (required)
  - technical_founder: boolean (required)
  - in_school: boolean (required)
  - commit_exclusively: boolean (required)
  - age: integer (optional)
  - gender: string (optional)
  - city: string (optional)
  - education: array of objects with properties {institution: string, degree: string, field: string, year: integer} (optional)
  - work_history: array of objects with properties {company: string, title: string, start_year: integer, end_year: integer, description: string} (optional)
  - hacked_system: string (optional)
  - impressive_thing: string (optional)
  - built_things: string (optional)
  - accolades: string (optional)

IMPORTANT: education items use 'institution' (not 'school') and 'year' (not 'graduation_year')
IMPORTANT: work_history items use 'title' (not 'role')

Evaluation criteria:
1. Role clarity and non-overlapping responsibilities
2. Complementary skill sets (technical + business)
3. Equity distribution fairness and alignment
4. Mix of technical and non-technical founders
5. Clear leadership structure
6. Diversity of backgrounds and perspectives

Output: Probability distribution over founder groups