# Play Console form answers

## data-safety-railworld.csv

The Data safety questionnaire, as filed for RailWorld on 2026-09-10.

Play Console's Data safety page has **Export to CSV / Import from CSV**, and that is by far
the sane way to fill it: the form has 782 possible answers, re-renders as you answer, and
un-sets earlier answers if you click the wrong thing. The CSV is validated on import - a bad
value is refused with the exact question id, and nothing is changed.

To reuse for the next game: export a fresh CSV from that game (the ids are stable), copy the
`Response value` column across, and import.

Two values Play refused here, and why:

- `PSL_DATA_COLLECTION_COMPLIES_FAMILY_POLICY` - not answerable when the target audience is
  13+, because Families policy does not apply.

What RailWorld declares: Device or other IDs collected AND shared (AdMob uses the advertising
id for its own serving); App interactions, Crash logs and Diagnostics collected only (Firebase
is a service provider processing on our behalf, which is exempt from "shared"); encrypted in
transit; no accounts; data deletion by request at the privacy policy URL.
