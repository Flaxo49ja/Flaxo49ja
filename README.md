# Anayo Chibuike Anyafu

**Security research and detection engineering · Maputo, Mozambique**

I measure what is actually deployed in under-measured networks, then build the tooling to fix and monitor it. Most of my work starts with Mozambique and the wider SADC region, because the data usually does not exist yet.

---

## 47 / 100

That is the mean HTTP security header score across the 66 sites reachable during my 2026 scan of Mozambican and international websites.

- Mozambican sites averaged **38.2** against **52.7** for the global comparison set.
- **68.2%** of sites were missing at least two of the six recommended headers.
- **42 of the 68** Mozambican sites were unreachable at scan time: dead DNS, broken TLS certificates, and timeouts. A site that will not complete a handshake cannot protect anyone, which makes this a finding in itself.

Method: roughly 100 sites across government, financial, educational and commercial sectors, one HTTPS GET each, six headers scored correct / weak / missing, with chi-square tests across categories. The whole pipeline is open and reproducible end to end.

→ **[header-study](https://github.com/Flaxo49ja/header-study)** · the scanner, the dataset, and the full results

---

## What I build

### [PhishGuard](https://github.com/Flaxo49ja/phishguard) — phishing detection that never phones home

A logistic regression trained on **107,355 real URLs** (48,338 verified PhishTank phishing, 59,017 legitimate Tranco links), using **18 lexical and structural features** extracted from the URL string alone. No page fetching, no reputation calls.

The model is exported to a ~2 KB JSON file and runs **entirely in your browser**, so a pasted URL never leaves the page. Every verdict comes with an occlusion explanation showing which features moved the probability. ROC-AUC **0.954**. Golden-master tests pin the JavaScript output to the Python model so the two can never drift apart.

### [nightshift](https://github.com/Flaxo49ja/nightshift) — a SOC range with ground truth

Most SOC projects teach you to install a SIEM. This one builds the part that actually matters: a loop that can tell you whether your detections work.

It collects **real telemetry** from journald and auditd on a single Linux host, applies JSON detection rules mapped to MITRE ATT&CK, gives you a triage queue where every dismissal is recorded with a reason, and then injects safe loopback-only simulations so detections can be scored against ground truth. 177 tests. On the sample run it reports 100% recall and **33% precision** — because two of three alerts were noise, and a scorer that hides that is not worth running.

### [header-study](https://github.com/Flaxo49ja/header-study) — the research above

Full methodology, sample definition, per-site results, and four charts. Built for Research Methodology (RM_2026-ii) at Universidade São Tomás de Moçambique, and published so anyone can re-run it or point it at their own country.

---

## Also building

- **[ioc-triage](https://github.com/Flaxo49ja/ioc-triage)** — triage an IP, domain, URL or hash across VirusTotal, AbuseIPDB, AlienVault OTX, urlscan.io and GreyNoise into one deterministic, explainable score. Never an LLM, scriptable exit codes, 24-hour SQLite cache so free tiers are not burned.
- **[mz-threat-feed](https://github.com/Flaxo49ja/mz-threat-feed)** — daily IOC feed cross-referenced against ASN prefixes registered to Mozambique and SADC, each verified against RIPEStat, published as an [auto-updating dashboard](https://flaxo49ja.github.io/mz-threat-feed/) by GitHub Actions.
- **[secbasics](https://github.com/Flaxo49ja/secbasics)** — [plain-language security and privacy guides](https://flaxo49ja.github.io/secbasics/) for people who are not security people.

---

## How I work

**Ground truth over vibes.** A detection you cannot score is a guess. Every project here either measures something real or is honest about what it cannot see.

**Publish the limitations.** Each README has a limitations section: unreachable sites are excluded from rates, one host is one vantage point, `sudo -n` writes nothing to the journal. Stating the boundary is part of the result.

**Reproducible or it did not happen.** Deterministic scoring, offline test suites, pinned inputs, and no network access in tests.

**Defensive only.** Everything here is built to measure, detect and defend. Nothing in these repositories attacks a system I do not own.

---

## Contact

- GitHub: [@Flaxo49ja](https://github.com/Flaxo49ja)
- Open to security engineering, detection engineering and research collaboration, in Mozambique or remote.
