{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- The Encounter resource can represent a clinical indication with `Encounter.reasonCode`, or a reference with `Encounter.reasonReference` to a Condition or other resource.