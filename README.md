# CSC 786 Reproducibility Demo: NASA Near Earth Objects

## Purpose
Demonstrates an ethical, reproducible data-collection workflow. The notebook pulls one week of
asteroid close-approach records from NASA's NeoWs API, saves a cleaned CSV, and logs provenance.

## Data source
- NASA Near Earth Object Web Service (NeoWs), https://api.nasa.gov
- Endpoint: `https://api.nasa.gov/neo/rest/v1/feed`
- Parameters: `start_date=2026-10-01`, `end_date=2026-10-07` (fixed, so results are repeatable)
- Data credit: NASA / JPL Center for Near Earth Object Studies

## How to run
1. Open the notebook in Google Colab.
2. Get a free API key at https://api.nasa.gov (or press Enter to use `DEMO_KEY`, which is limited to a few calls per hour).
3. Run all cells except those marked *Author only*.
4. Output: `data/processed/neo_2026-10-01_to_2026-10-07.csv` plus a new log line in `DATA_README.md`.

## Files
| File | Purpose |
|------|---------|
| `*.ipynb` | Collection notebook |
| `README.md` | This overview |
| `ETHICS.md` | Ethical statement |
| `DATA_README.md` | Provenance log (endpoint, params, timestamp, SHA-256, versions) |
| `requirements.txt` | Library versions used |
| `data/processed/` | Cleaned CSV (committed) |
| `data/raw/` | Full JSON responses (ignored by git) |
| `LICENSE` | MIT license for the code |

## Expected variability
The date range is fixed, so record counts and asteroid IDs should match. NASA occasionally refines
orbit estimates, so distance or velocity values could change slightly over time, which would change
the file hash. Compare against the logged hash in `DATA_README.md`.

## Reflection
The NASA API call and provenance logging worked after a few minor tweaks.
The main problem was pushing from Colab: the remote URL was saved with a blank repo name because Colab doesn’t 
fill in Python variables on a line that also uses a shell variable like $GITHUB_TOKEN. 
I fixed it by using environment variables for the whole URL and git remote set-url to repair the saved remote.

