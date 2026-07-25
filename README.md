# PII Redaction Tool

Scaler assignment. Reads a .docx (Red Herring Prospectus), finds PII, replaces it with fake values.

I stuck to regex + pulling names/companies out of the document (promoters, contact persons, Limited/LLP etc). No spaCy or Presidio.

**Detects:** names, emails, phones, companies, addresses, SSN, credit cards, DOB, IPs

**Left alone:** CIN, order/ticket style ids, boilerplate like "Equity Shares"

## setup

```
pip install -r requirements.txt
```

## run

```
python redact_pii.py -i "Red Herring Prospectus.docx" -o submission/Red_Herring_Prospectus_REDACTED.docx
python evaluate.py
```

## what’s in submission/

- `Evaluation_Strategy_and_Metrics.docx` — how I scored it + precision/recall
- `Red_Herring_Prospectus_REDACTED.docx` — redacted output

Same real string always maps to the same fake one so the file stays readable.
