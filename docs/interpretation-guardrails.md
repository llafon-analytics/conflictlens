# Interpretation guardrails

ConflictLens deals with politically and historically sensitive data. The following guardrails define how the project should be read.

## 1. A country-year contributor is not a perpetrator

When the analysis says that a country-year contributes a share of annual deaths, it means only that deaths are coded under that analytical unit and year in the underlying data.

It does not identify:

- who killed whom;
- who was targeted;
- the nationality of victims;
- the responsible actor;
- legal responsibility;
- moral responsibility;
- the historical character of the violence.

The country-year is a bookkeeping grain, not a perpetrator attribution.

## 2. A share of annual deaths is not a verdict

A high contribution to an annual total is an arithmetic statement. It should not be read as a ranking of atrocities, a hierarchy of suffering, or a legal assessment.

## 3. Descriptive categories are not legal classifications

Terms such as genocide, civil war, interstate war and civilian-exposure rupture are used as descriptive categories to explain why similar-looking totals can reflect different kinds of events.

Unless explicitly stated otherwise, these labels are not legal determinations.

## 4. Aggregate curves hide composition

A global annual curve can show the shape of the recorded toll, but it cannot explain the underlying composition by itself.

The same annual total can combine:

- one dominant mass-fatality event;
- several unrelated wars;
- civilian-dominated violence;
- mostly combatant or non-civilian fatalities;
- different source definitions and coding rules.

Composition must be inspected before interpretation.

## 5. UCDP and ACLED are not interchangeable

UCDP and ACLED are both valuable, but they do not measure the same thing in the same way.

ConflictLens uses UCDP as the primary source for the first article's headline organized-violence death figures and ACLED as a complementary benchmark.

Disagreement between sources should be treated as a source-comparison signal, not automatically as an error.

## 6. `NA` and `0` are not the same

Missing data should not be silently treated as zero. A zero can be analytically meaningful only when the source universe, unit existence and coverage rules justify it.

The notebooks therefore use guarded zero-fill logic and keep coverage flags visible.

## 7. Unit existence matters

A unit-year that does not exist in the relevant analytical sense should not be interpreted as a peaceful observation.

The `unit_exists_in_year` guard is used to avoid turning pre-existence, post-existence or non-applicable rows into false zeros.

## 8. Counts and rates answer different questions

Raw counts show where the recorded toll accumulates. Per-capita rates show relative intensity under population assumptions.

Neither is a complete description of severity.

## 9. Concentration is not rarity

Finding that deaths are concentrated in a small number of years or unit-years does not mean that violence is rare, unimportant elsewhere, or socially contained.

It means that the recorded fatality toll is highly unevenly distributed.

## 10. This is not a prediction system

ConflictLens does not claim to forecast conflict onset, escalation, mass violence or future fatalities.

Any later modeling extension should be interpreted as exploratory benchmarking unless explicitly validated for a narrower purpose.

## 11. This is not a substitute for historical analysis

Data can reveal structure and anomalies. It cannot replace historical, political, actor-level and event-level analysis.

The correct use of this project is to identify where to look closer, not to treat the panel as a final explanation.
