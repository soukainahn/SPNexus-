# How to use pySPN safely on an HTB / lab machine

**Prereqs**
- A lab AD environment under your control (HTB machine or local lab).
- Python 3.10+ and a virtualenv.

**Step 1 — install**
```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

**Step 2 — run**
```
python -m pyspn.cli collect --dc <DC_IP> --user "LAB\Administrator" --password "Passw0rd!" --out spns.csv --bloodhound spns-bh.json
```

**Step 3 — import to BloodHound**
1. Open BloodHound (running in your lab).
2. Menu → Upload Data → select `spns-bh.json`.
3. Use the graph to investigate relationships; SPNs can indicate service accounts to review.

**Notes**
- `pySPN` does **not** perform kerberoasting or any exploitation. It only enumerates and annotates.
- Use the `examples/sample_spns.json` to practice importing without touching a live DC.
