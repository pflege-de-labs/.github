# Security policy

This is the default security policy for repositories in
[pflege-de-labs](https://github.com/pflege-de-labs). A repository with its own `SECURITY.md`
adds to it, for example with supported versions and deployment advice.

## Reporting a vulnerability

Report vulnerabilities privately through GitHub, never in a public issue, pull request or
discussion: open the repository's **Security** tab and choose **Report a vulnerability**.

Helpful in a report:

- what an attacker can reach or change, and what access they need to start
- the affected version: a release tag or a commit
- the smallest reproduction you have

## What happens next

- We acknowledge a report within **3 working days**.
- Within **10 working days** we tell you whether we consider it a vulnerability, how severe we
  think it is, and what we intend to do.
- We develop the fix in a private fork of the advisory, publish a release and then the advisory,
  with a CVE where one applies. We credit you unless you ask us not to.

Please give us the chance to ship a fix before you disclose publicly. If we have not responded
within the times above, say so in the report.

## Supported versions

Unless a repository says otherwise, fixes go onto `main` and into the next release. Older
releases are not patched; run the newest one.

## Verifying releases

Where a project signs its releases, its README explains how to verify them.
