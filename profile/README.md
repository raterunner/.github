# RateRunner

**Open-source Pricing as Code for SaaS.**

Manage pricing plans, subscription configuration, feature entitlements, limits, and promotions as code — without manually maintaining your Stripe dashboard.

RateRunner brings your SaaS billing configuration into version control. Define everything in YAML, review changes through pull requests, validate your configuration, and sync it with Stripe using a simple CLI.

## Why RateRunner?

Pricing is part of your product. It should live in your codebase, not be scattered across billing dashboards and application logic.

- **Single source of truth** — Define plans, prices, limits, entitlements, and promotions in YAML.
- **Git-native workflow** — Review and track pricing changes alongside your code.
- **Safe deployments** — Validate configurations and preview changes before applying them.
- **Stripe integration** — Synchronize products, prices, coupons, and promotion codes.
- **Open source** — MIT licensed, built with Go.

## Installation

RateRunner is available for **macOS, Linux, and Windows**, with builds for Intel/AMD (`amd64`) and ARM (`arm64`).

### macOS

Install with [Homebrew](https://brew.sh/):

```sh
brew install raterunner/tap/raterunner
```

Alternatively, download a `darwin` archive from [GitHub Releases](https://github.com/raterunner/cli/releases/latest): choose `arm64` for Apple Silicon or `amd64` for Intel Macs. Extract it and move `raterunner` to a directory on your `PATH`, such as `/usr/local/bin`.

### Linux

If you use Homebrew on Linux:

```sh
brew install raterunner/tap/raterunner
```

Otherwise, download a package for your distribution from [GitHub Releases](https://github.com/raterunner/cli/releases/latest):

- **Debian / Ubuntu:** `.deb`
- **Fedora / RHEL:** `.rpm`
- **Alpine:** `.apk`

Install it with your distribution's package manager. Choose `amd64` for x86-64 systems or `arm64` for ARM64 systems.

You can also download the matching `linux` `.tar.gz` archive, extract it, and install the binary from the extracted directory:

```sh
sudo install -m 755 raterunner /usr/local/bin/raterunner
```

### Windows

1. Download `raterunner_VERSION_windows_amd64.zip` or `raterunner_VERSION_windows_arm64.zip` from [GitHub Releases](https://github.com/raterunner/cli/releases/latest). `VERSION` represents the release number; choose the archive matching your processor.
2. Extract the ZIP into a folder such as `C:\Tools\RateRunner`.
3. Add the folder containing `raterunner.exe` to your user `Path` under **Environment Variables**.
4. Open a new PowerShell or Command Prompt window.

### Verify installation

On any platform:

```sh
raterunner --version
```

For more options, see the [CLI installation instructions](https://github.com/raterunner/cli#installation).

## Get started

Initialize your pricing configuration:

```sh
raterunner init
```

Edit the generated `raterunner/billing.yaml` to define your pricing, then validate it:

```sh
raterunner validate raterunner/billing.yaml
```

Set your Stripe test API key before previewing changes.

**macOS / Linux:**

```sh
export STRIPE_SANDBOX_KEY="sk_test_..."
```

**Windows (PowerShell):**

```powershell
$env:STRIPE_SANDBOX_KEY = "sk_test_..."
```

Preview changes without modifying Stripe:

```sh
raterunner apply --env sandbox --dry-run raterunner/billing.yaml
```

## Explore the project

- [RateRunner CLI](https://github.com/raterunner/cli) — Command-line tool for managing billing as code.
- [RateRunner Schema](https://github.com/raterunner/schema) — YAML configuration schemas.
- [Homebrew Tap](https://github.com/raterunner/homebrew-tap) — Package distribution.

**[Website](https://www.raterunner.run/) · [Documentation](https://www.raterunner.run/docs) · [GitHub](https://github.com/raterunner/cli)**

*Currently supports Stripe. Additional payment providers are planned.*

---

**Stop managing pricing in dashboards. Start managing it in code.**
