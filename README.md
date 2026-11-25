# Anayo Chibuike Anyafulu

Security research and detection engineering. Maputo, Mozambique.

Most of what I do starts with a count. How many sites actually send the headers they
should. Which phishing URLs fail the same three checks. How much malicious traffic lands
in address space registered in southern Africa. Those are questions with answers, and the
answers usually are not written down anywhere yet.

The repositories below are the tools I built to get those numbers. They are written so
that someone else can run them and disagree with the result.

[Portfolio](https://flaxo49ja.github.io/portfolio/) · [Email](mailto:chibuikeanyafulu@gmail.com)

## Security work

| Repository | What it does |
| --- | --- |
| [header-study](https://github.com/Flaxo49ja/header-study) | Scans roughly 100 Mozambican and international sites, scores six HTTP security headers, and keeps the unreachable hosts in the dataset instead of discarding them. Written for RM_2026-ii at USTM. |
| [phishguard](https://github.com/Flaxo49ja/phishguard) | Phishing detection that runs in the browser. A logistic regression over 18 features of the URL string, trained on 107,355 URLs, with no network call at inference time. |
| [nightshift](https://github.com/Flaxo49ja/nightshift) | A single-machine SOC range. Collects real journald and auditd telemetry, applies JSON rules, injects loopback-only techniques with the ground truth saved first, then scores precision and recall against it. |
| [ioc-triage](https://github.com/Flaxo49ja/ioc-triage) | One deterministic verdict for an IP, domain, URL or hash, built on five free intel sources. |
| [mz-threat-feed](https://github.com/Flaxo49ja/mz-threat-feed) | Daily IOCs cross-referenced against ASN prefixes registered to Mozambique and SADC, published as a dashboard by GitHub Actions. |
| [secbasics](https://github.com/Flaxo49ja/secbasics) | Plain-language security and privacy guides for readers who do not work in security. |

## Other things

- [pc-doctor](https://github.com/Flaxo49ja/pc-doctor) — check a used PC before buying it: CPU, RAM, SMART, battery, keyboard, display.
- [wifi-watchdog](https://github.com/Flaxo49ja/wifi-watchdog) — reconnects Wi-Fi when the negotiated link rate collapses, with a cooldown so it does not flap.
- [yard](https://github.com/Flaxo49ja/yard) — a study CLI in Rust. Focus to earn yard time.
- [scoutradar](https://github.com/Flaxo49ja/scoutradar) — flags football players outperforming their position, minutes and club context.
- [pitch-optimiser](https://github.com/Flaxo49ja/pitch-optimiser) — best XI under a transfer budget, drawn in the terminal.
- [my-stack](https://github.com/Flaxo49ja/my-stack) — one tool per category, with the reason attached.

## How the work is documented

Every README ends with what its result cannot see: hosts that never answered, a single
vantage point, a privilege that was not available on the test machine. Tests run offline,
scoring is deterministic, and nothing here touches a system I do not own.

## Contact

- Email: [chibuikeanyafulu@gmail.com](mailto:chibuikeanyafulu@gmail.com)
- Portfolio: [flaxo49ja.github.io/portfolio](https://flaxo49ja.github.io/portfolio/)
- GitHub: [@Flaxo49ja](https://github.com/Flaxo49ja)

Open to security engineering and detection engineering roles, in Mozambique or remote.
