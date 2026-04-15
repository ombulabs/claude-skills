# OmbuLabs Skills

A Claude Code plugin marketplace for Rails upgrade tooling by [OmbuLabs.ai](https://www.ombulabs.com), based on the [FastRuby.io](https://www.fastruby.io) methodology.

## Skills

| Skill | Description | Repo |
|-------|-------------|------|
| **dual-boot** | Dual-boot setup with `next_rails` gem for running two Rails/Ruby versions simultaneously | [claude-code_dual-boot-skill](https://github.com/ombulabs/claude-code_dual-boot-skill) |
| **rails-load-defaults** | Align `load_defaults` across Rails versions with safe, incremental config changes | [claude-code_rails-load-defaults-skill](https://github.com/ombulabs/claude-code_rails-load-defaults-skill) |
| **rails-upgrade** | Plan and execute Rails version upgrades following FastRuby.io methodology | [claude-code_rails-upgrade-skill](https://github.com/ombulabs/claude-code_rails-upgrade-skill) |

## Installation

```bash
# Add marketplace
claude plugin marketplace add https://github.com/ombulabs/claude-skills.git

# Install skills
claude plugin install dual-boot@ombulabs-skills
claude plugin install rails-load-defaults@ombulabs-skills
claude plugin install rails-upgrade@ombulabs-skills
```

## Usage

After installation, skills are available as slash commands:

- `/dual-boot:dual-boot` - Set up dual-boot with next_rails
- `/rails-load-defaults:rails-load-defaults` - Align load_defaults config
- `/rails-upgrade:rails-upgrade` - Run a full Rails upgrade

## Dependency Chain

```
rails-upgrade
  ├── rails-load-defaults  (load_defaults alignment)
  └── dual-boot            (dual-boot setup with next_rails)
```

All three skills should be installed together. The `rails-upgrade` skill references the other two during a full upgrade workflow.

## License

MIT
