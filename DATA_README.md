# Data Provenance Log

Each line below is one collection run, written automatically by the notebook.
Fields: timestamp_utc, endpoint, params (API key excluded), raw and processed file names,
record count, SHA-256 of the processed CSV, and library versions.

---

- {"timestamp_utc": "2026-10-26T050939Z", "endpoint": "https://api.nasa.gov/neo/rest/v1/feed", "params": {"start_date": "2026-10-01", "end_date": "2026-10-07"}, "key_type": "personal (free tier)", "raw_file": "neo_raw_2026-10-01_to_2026-10-07_2026-10-26T050939Z.json", "processed_file": "neo_2026-10-01_to_2026-10-07.csv", "records": 34, "sha256": "166dc7820b1fbf7a794f1e0e1fcb657fcfe963c19fc0f105bbcb4266575fa80e", "python": "3.13.16", "pandas": "2.2.3", "requests": "2.32.4"}