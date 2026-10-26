# Ethical Statement

- **Source and license:** Data comes from NASA's public NeoWs API. NASA data is generally free of
  copyright restrictions; NASA/JPL is credited as the source in README.md.
- **Privacy:** No personally identifiable information. Records describe asteroids only.
- **Terms and rate limits:** One API call per run, with a timeout and exponential backoff on errors
  or HTTP 429. Well under NASA's limit of 1,000 requests per hour per key.
- **Secrets:** The API key is entered with `getpass` at runtime. It is never stored in code, in
  outputs, in `DATA_README.md`, or in git history. `.env` files are git-ignored.
- **Provenance:** Every run logs endpoint, parameters (minus the key), timestamp, file hash, and
  library versions in `DATA_README.md`.

## Potential risks
- Low ethical risk overall. The main risk is misinterpretation, for example treating
  "potentially hazardous" as "likely to hit Earth". It is a NASA classification based on size and
  orbit distance, not an impact prediction.

## Mitigations
- Fields are kept with their original NASA names and units (km, km/h) so nothing is relabeled.
- Only a small, one-week sample is stored.

## Limitations
- One week of data is a demo sample, not representative of all near-Earth objects.
- Values depend on NASA's current orbit solutions, which can be revised.
