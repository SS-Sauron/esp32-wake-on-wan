```markdown
# Contributing to ESP32 Wake-on-WAN Relay

First off, thanks for taking the time to contribute! 🎉

## Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating a bug report, please check existing issues. Include:

- ESP32 board model & Arduino core version
- Steps to reproduce
- Full serial output
- Expected vs. actual behaviour

### Suggesting Enhancements

Open a feature request with the `enhancement` label. Include the problem, proposed solution, and alternatives.

### Your First Code Contribution

Look for issues tagged `good first issue`. For code changes:

1. Fork the repo.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make changes, test on real ESP32.
4. Commit with a clear message.
5. Push to your fork and open a Pull Request against `main`.

### Development Setup

- Arduino IDE (or PlatformIO) with ESP32 board support (≥2.0.14)
- Libraries: PubSubClient, WiFiClientSecure (built‑in)
- Create a `config.h` with your credentials – never commit it.

### Style Guide

- Use `snake_case` for functions/variables.
- Indent with 2 spaces.
- Use `DEBUG_PRINT` macros for logging.
- Avoid `String` in callbacks; use `char*` and `memcmp`.

## Getting Help

Open a Discussion on GitHub or join our [Discord](https://discord.gg/example).

Thank you for contributing!