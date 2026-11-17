# Security Policy

## Reporting a vulnerability

Do not publish exploit details, credentials, private datasets, personal data, or unpatched vulnerabilities in a public issue or pull request.

Use the repository's **Security** tab and select **Report a vulnerability** to submit a private report when that feature is available. If private vulnerability reporting is unavailable, contact the maintainer privately through https://github.com/shxamill.

## Model-file warning

The application loads Python pickle files. Pickle deserialization can execute code. Only load model artifacts whose source you trust; do not accept or load untrusted .pkl files.

## Scope

This is an educational project and does not provide production security or availability guarantees. Please allow the maintainer a reasonable opportunity to investigate before making a report public.
