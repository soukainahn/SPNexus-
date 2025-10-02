# pySPN

**pySPN — Service Principal Name discovery & BloodHound exporter (lab-only)**

A tiny, importable Python library + CLI that performs **read-only** LDAP discovery of Service Principal Names (SPNs) in an Active Directory domain, annotates findings with short detection/remediation hints, and exports results as CSV, JSON and BloodHound-compatible JSON.

**⚠️ WARNING — LAB ONLY**  
This project performs read-only LDAP queries. Do **NOT** run it against systems you do not own or have explicit authorization to test.

---

## Features (MVP)
- Small library API (`pyspn.collector.get_spns(...)`)
- CLI: `pyspn collect --dc ... --user ... --password ...`
- Export formats: CSV, JSON, BloodHound JSON
- Example dataset: `examples/sample_spns.json`
- Unit tests (mocked LDAP) + GitHub Actions CI

---

## Quickstart

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
# or: pip install -e .
```

Run collector (example):

```bash
python -m pyspn.cli collect --dc 192.168.36.155 --user "LAB\Administrator" --password "P@ssw0rd" --out spns.csv --json spns.json --bloodhound spns-bh.json
```

Import `spns-bh.json` into BloodHound (Menu → Upload Data).

---

## Example usage as library

```python
from pyspn import collector
entries = collector.get_spns("dc.example.local", "EXAMPLE\\labuser", "Secret123")
for e in entries:
    print(e.sam, e.spns)
```

---

## Contributing & Code of Conduct
See `CONTRIBUTING.md` (add later). By contributing you agree to keep this repo lab-only and not add offensive features.

## License
MIT — see `LICENSE`
