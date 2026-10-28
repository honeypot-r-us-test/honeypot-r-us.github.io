# Honeypot R Us public site

- This repository is the static Astro marketing site only.
- Customer and organization workflows belong to the HNPT web server; authentication belongs to the Shared Auth proxy. The site delegates to those services and never handles credentials.
- Keep user and organization login links public, but do not advertise administrative entry points.
- Present only verified capabilities as available. Label in-development and planned deception features explicitly.
- Preserve a responsive, keyboard-accessible sticky header and durable footer.
- Keep the source commit identical between the test and production organization Pages repositories. Derive the Pages origin from the build environment.
- Validate in `honeypot-r-us-test` before promoting the exact reviewed commit to `honeypot-r-us`.
- `.zpkg.toml` is the package/test contract; `package.json` and `package-lock.json` are the locked npm build adapter.
- This site has no command surface, so a `flags-2-env` flag contract is intentionally not added.
- Never commit credentials, Cloudflare tokens, Shared Auth secrets, production data, or attacker-controlled evidence.

<!-- BEGIN ores-agents-pointer: managed by ORESoftware/my-ai; edit there, not here -->

## Canonical agent instructions

Before doing anything else in this repository, also read:

    .ores/agents/AGENTS.md

That path is a symlink to `~/codes/oresoftware/my-ai/AGENTS.md`, whose canonical copy is
<https://github.com/ORESoftware/my-ai/blob/main/AGENTS.md>.

It exists at a fixed path *inside* the repository because some agents cannot walk up past
the repository root, so machine-wide instructions one or more directories above are
invisible to them. This pointer plus that path make the same file reachable from a working
directory anywhere in the tree.

The symlink is deliberately **not committed**: it names an absolute path that is only valid
on a machine with `~/codes/oresoftware/my-ai` checked out, so committing it would produce a
broken link for everyone else and for CI. `.ores/` is git-ignored for that reason. If
`.ores/agents/AGENTS.md` is missing on your machine, create it with:

    mkdir -p .ores/agents
    ln -sfn "$HOME/codes/oresoftware/my-ai/AGENTS.md" .ores/agents/AGENTS.md

or run `~/codes/oresoftware/my-ai/scripts/link-repo-agents.sh` once to do it for every git
repository under `~/codes`, and `--check` to verify them.

A missing `.ores/agents/AGENTS.md` is a setup gap on the reader's machine, never a reason to
skip the canonical instructions: fetch them from the URL above instead.

<!-- END ores-agents-pointer -->
