# Install Agent Readiness Gate

[Install on your Jira test site](https://developer.atlassian.com/console/install/471ccf82-e18e-4714-a55c-0bf8c2909eb2?signature=AYABeCg2d3lsH8FLZPENkBY5sVoAAAADAAdhd3Mta21zAEthcm46YXdzOmttczp1cy13ZXN0LTI6NzA5NTg3ODM1MjQzOmtleS83MDVlZDY3MC1mNTdjLTQxYjUtOWY5Yi1lM2YyZGNjMTQ2ZTcAuAECAQB4CxqLTo9l4lqXuFjNim1xJM%2Bp%2F3TVP9xHS2BrU5DRRucBYHEt8yEwPiRE3n6fWU%2BwGwAAAH4wfAYJKoZIhvcNAQcGoG8wbQIBADBoBgkqhkiG9w0BBwEwHgYJYIZIAWUDBAEuMBEEDLO54PmSIvbIJDR4bQIBEIA7A6lnklJ37U1EQ35VEvEGlBNdTUUJa6clha92oo0ThZwbIvGdzjki7HbT%2BK5at7dMRrchqienkxxD1DcAB2F3cy1rbXMAS2Fybjphd3M6a21zOmV1LXdlc3QtMTo3MDk1ODc4MzUyNDM6a2V5LzQ2MzBjZTZiLTAwYzMtNGRlMi04NzdiLTYyN2UyMDYwZTVjYwC4AQICAHi9bVMAkme4qVQX1fQHo6ePw3H40A7cGfz7yrmSfBWMXgEkc2qrf0KUd9ORteu7A8UOAAAAfjB8BgkqhkiG9w0BBwagbzBtAgEAMGgGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMsVpXgNF5TwxGeXCYAgEQgDt0ZYw00eilpspjsZh3P%2BqEdAu9g0oVlFtc3Rs%2Fakc%2F1i7g3Hy3UL9j2LfpflJKKbSxjBhR6WAY6xLbdwAHYXdzLWttcwBLYXJuOmF3czprbXM6dXMtZWFzdC0xOjcwOTU4NzgzNTI0MzprZXkvNmMxMjBiYTAtNGNkNS00OTg1LWI4MmUtNDBhMDQ5NTJjYzU3ALgBAgIAeDYASx0XCjkny4iLV6vz%2BKtEGSGT6kdt0QRpkn6D%2FlVEAXwxj1MHR1L3k8oWij4l%2BS0AAAB%2BMHwGCSqGSIb3DQEHBqBvMG0CAQAwaAYJKoZIhvcNAQcBMB4GCWCGSAFlAwQBLjARBAwwd7Hr%2BKjBufP6wQUCARCAO%2FQIZlq3ZlOLR7r6BJ6MH3ysxPN7A1D%2FPCLELcwWT1HNNrolFwvyHtPkUUVOMFO9USIQurY1mfKt6mo3AgAAAAAMAAAQAAAAAAAAAAAAAAAAAB4f0j0JWIIfrW%2F1LIzppT%2F%2F%2F%2F%2F%2FAAAAAQAAAAAAAAAAAAAAAQAAADLYw023EUTuk0iLxubK%2FIOLUlVQFqXrdPONBc5p%2BH7UxNGY3M3AXGC9jFegxuDBj%2BMT5rOqx4vLyB%2ByPRUtXIfLhI4%3D&product=jira)

This is the actual Forge distribution link tested on a separate Jira site on 6 November 2026. A site administrator must review and accept the displayed Jira read/write and app-storage scopes. Use synthetic data only. The source code repository is private; no developer API key, local checkout, tunnel, or external model account is needed.

Create a Jira software project and a synthetic issue. In the issue's Apps menu, open **Agent Readiness Gate**. Follow the [walkthrough](README.md). The reviewer needs **Edit Issues** and **Administer Projects** permissions in that project; site administration alone may not grant the project permission. On a new company-managed project, confirm the reviewer has the project Administrators role before the approval step.

Production 2.0.0 was installed through this link on the independent test site. Empty state, blocked import, reload, repaired evidence, explicit approval to READY, regression to BLOCKED, four history snapshots, and duplicate-safe remediation all passed. The same owner account was used across two distinct sites; alternate-account and hidden-issue tests were not performed live.

Optional Rovo requires availability on your Atlassian site. The core Jira panel works without it. The read-only advisor was verified separately on the development site.

Read the [privacy information](privacy.md) and [evaluation terms](terms.md) before installation.


Current deployment (7 November 2026): production 2.2.0. Existing-installation release/history reads were verified. Production-specific runner/Rovo acceptance and clean-install testing of this version are not yet complete.
