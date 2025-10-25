# Audit-framework
Compliance automation with Python and PowerShell
## ✅ Tested On

- Ubuntu 22.04 LTS - Full functionality
- Ubuntu 20.04 LTS - Full functionality  
- Debian 11 - Partial (no UFW by default)
- RHEL 8 - Partial (uses firewalld instead of UFW)

## ⚠️ Known Working Configurations

| Check | Ubuntu | Debian | RHEL | Notes |
|-------|--------|--------|------|-------|
| File Permissions | ✅ | ✅ | ✅ | Works everywhere |
| Password Policy | ✅ | ✅ | ✅ | Requires /etc/login.defs |
| Firewall (UFW) | ✅ | ⚠️ | ❌ | Debian: install UFW; RHEL: use firewalld |
| Services | ✅ | ✅ | ✅ | Requires systemd |
```

### Final Pre-Commit Checklist:

- [ ] Ran test suite successfully
- [ ] Ran actual audit and verified output files
- [ ] Checked JSON output is valid (`cat output.json | jq .`)
- [ ] Opened HTML report in browser
- [ ] Added `.gitignore` for sensitive outputs:
```
  audit_reports/
  audit_output/
  *.json
  *.csv
  *.html
  __pycache__/
  *.pyc
```
- [ ] Added LICENSE file (MIT recommended)
- [ ] README clearly states tested environments
- [ ] Added example output in `examples/` directory (sanitized)

### Sample Directory Structure for GitHub:
```
your-repo/
├── .github/
│   └── workflows/
│       └── test.yml
├── .gitignore
├── README.md
├── LICENSE
├── compliance_audit.py
├── test_audit_environment.py
├── ComplianceAudit.ps1  (if including PowerShell)
└── examples/
    ├── sample_output.json (sanitized)
    └── sample_report.html (sanitized)
