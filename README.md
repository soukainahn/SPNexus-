# SPNexus

  ____  ____  _   _  _   _  _   _  ____  _  __
 / ___|/ ___|| \ | || \ | || \ | |/ ___|| |/ /
| (___| |    |  \| ||  \| ||  \| | |    | ' / 
 \___ \ |    | . ` || . ` || . ` | |    | . \ 
  ___) | |___ | |\  || |\  || |\  | |___ | |\ \
 |____/ \____||_| \_||_| \_||_| \_|\____||_| \_\

SPNexus — Service Principal Name discovery & BloodHound exporter (lab-only)

---

WARNING — LAB ONLY  
SPNexus performs read-only LDAP queries against Active Directory. Do not run it against systems you do not own or do not have explicit authorization to test.

---

Features

- Small, importable Python library plus a command-line interface  
- Enumerates Service Principal Names (SPNs) in Active Directory  
- Exports results as CSV, JSON, and BloodHound-compatible JSON  
- Adds detection hints and remediation advice for each finding  
- Includes unit tests (mocked LDAP) and a GitHub Actions CI workflow



