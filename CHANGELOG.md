# CHANGELOG

## Version 0.5.0

  * [**NEW**] Introduced **circuit-breaker** functionality
  * [**BREAKING**] Metrics format: with the introduction of the
    *circuit-breaker* function I've restructured the metrics names and
    added new metrics, therefore if you rely on the old metrics name
    structure you might need to update your alerts. See the
    [tracking](./doc/tracking.md) page.
  * [**CHANGED**] Default retry policy changed from
    `[:random-exp-backoff :base 3000 :+/- 0.50]` to
    `[:random-exp-backoff :base 300 :+/- 0.50 :max 60000]` to
    accommodate wider type of use cases with the default case.
  * [**DEPRECATION**] From `v0.5.0-alpha7`, the `:max-retry` option is
    *deprecated* in favour of `:max-retries`. The old version will
    still work with the same behaviour, but display a warning message
    at compile time.  It will be removed in future releases.
