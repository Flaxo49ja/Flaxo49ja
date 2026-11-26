# Anayo Chibuike Anyafulu

Detection engineer in Maputo, Mozambique. I build security tools and then score them against ground truth.

Most of what I do starts with a count. How many sites actually send the headers they
should. Which phishing URLs fail the same three checks. How much malicious traffic lands
in address space registered in southern Africa. Those are questions with answers, and the
answers usually are not written down anywhere yet.

The repositories below are the tools I built to get those numbers. Each one carries its
result and what that result cannot see; they are written so someone else can run them and
disagree with the number.

[Portfolio](https://flaxo49ja.github.io/portfolio/) · [Email](mailto:chibuikeanyafulu@gmail.com)

## Security work

| Repository | What it does | Result |
| --- | --- | --- |
| [nightshift](https://github.com/Flaxo49ja/nightshift) | A single-machine SOC range. Collects real journald and auditd telemetry, applies JSON rules, injects loopback-only techniques with the ground truth saved first, then scores precision and recall against it. | 100% recall on 1 scorable technique; precision 33% → 100% once scoring was scoped to the injection window, same events. 186 offline tests. |
| [phishguard](https://github.com/Flaxo49ja/phishguard) | Phishing detection that runs in the browser. A logistic regression over 18 features of the URL string, trained on 107,355 URLs, with no network call at inference time. | ROC-AUC 0.954, 2 KB model, per-feature occlusion explanations, zero requests leaving the page. |
| [mz-threat-feed](https://github.com/Flaxo49ja/mz-threat-feed) | Daily IOCs cross-referenced against ASN prefixes registered to Mozambique and SADC, published as a dashboard by GitHub Actions. | One run: 5,400 indicators checked, 4,055 prefixes watched, 103 indicators on SADC-registered address space. |
| [ioc-triage](https://github.com/Flaxo49ja/ioc-triage) | One deterministic verdict for an IP, domain, URL or hash, built on five free intel sources. | 5 sources → 1 weighted verdict, 24-hour SQLite cache, exit codes you can script. |
| [header-study](https://github.com/Flaxo49ja/header-study) | Scans 68 Mozambican and 40 international sites, scores six HTTP security headers, and keeps the unreachable hosts in the dataset instead of discarding them. Written for RM_2026-ii at USTM. | Mozambican sites averaged 38.2/100 against 52.7/100 internationally; 68.2% were missing two or more headers. |
| [secbasics](https://github.com/Flaxo49ja/secbasics) | Plain-language security and privacy guides for readers who do not work in security. | Four guides in Portuguese — home lab, VPN, everyday tools, privacy. |

## Other things

- [pc-doctor](https://github.com/Flaxo49ja/pc-doctor) — check a used PC before buying it: CPU, RAM, SMART, battery, keyboard, display.
- [wifi-watchdog](https://github.com/Flaxo49ja/wifi-watchdog) — reconnects Wi-Fi when the negotiated link rate collapses, with a cooldown so it does not flap.
- [yard](https://github.com/Flaxo49ja/yard) — a study CLI in Rust. Focus to earn yard time.

Also public: [scoutradar](https://github.com/Flaxo49ja/scoutradar), [pitch-optimiser](https://github.com/Flaxo49ja/pitch-optimiser), [my-stack](https://github.com/Flaxo49ja/my-stack).

## How the work is documented

Every README ends with what its result cannot see: hosts that never answered, a single
vantage point, a privilege that was not available on the test machine. Tests run offline,
scoring is deterministic, and nothing here touches a system I do not own.

## Contact

- Email: [chibuikeanyafulu@gmail.com](mailto:chibuikeanyafulu@gmail.com)
- Portfolio: [flaxo49ja.github.io/portfolio](https://flaxo49ja.github.io/portfolio/)
- GitHub: [@Flaxo49ja](https://github.com/Flaxo49ja)

Open to security engineering and detection engineering roles, in Mozambique or remote.
