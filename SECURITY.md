# Security policy

Wunderlab runs tools and models on people's own machines, so we take security reports seriously.

## Reporting a vulnerability

Please **do not open a public issue.** Report privately in one of these ways:

- Use GitHub's **Report a vulnerability** button on the repository's Security tab (private vulnerability reporting).
- Email security@wunderlab.eu.

Include what you found, how to reproduce it, the version or commit, and the impact you expect. A minimal proof of concept helps a lot.

We aim to acknowledge reports within 7 days, keep you updated while we investigate, and credit you in the fix notes unless you prefer otherwise. Please give us reasonable time to fix an issue before publishing details.

## What we care about most

- Escapes from the sandboxed runtime or the virtual environment, including path traversal and access to files that were not linked
- Bypasses of the consent step for real-shell commands or file changes
- Ways to exceed an agent's step budget or the user's resource limits
- Authentication or account-creation flaws, especially for remotely accessible instances
- Prompt injection that leads to actions the user did not approve
- Unsafe handling of imported models and datasets
- Leaks of local conversations or files through the cloud offload path

## Supported versions

Wunderlab is in early development. Security fixes go to the `main` branch and to the latest release once releases exist.

## Out of scope

Issues that require an already-compromised machine, social engineering of maintainers, or denial of service by a user who has already been granted the resources involved.
