# Data Pipeline Organizer
A production-inspired Bash automation script that organizes
incoming CSV data files through a structured pipeline workflow.
Built as part of my Data Engineering learning journey.

---

## The Problem It Solves
In real data engineering environments, new data files arrive
constantly in a landing/incoming folder. Someone or something
needs to:
- Detect new files automatically
- Validate them before processing
- Organize them into the correct folders
- Reject invalid files safely
- Log every action for debugging and auditing
This script automates that entire workflow.

---
## How It Works
incoming/        ← new CSV files land here

↓

[validation]     ← is the file empty? does it have data rows?

↓

raw/             ← valid files moved here with date stamp

rejected/        ← empty or invalid files moved here

logs/            ← every action logged with timestamp

---

## Project Structure
data_pipeline_organizer/

├── data/
│     ├── incoming/          New files land here
│     ├── raw/               Valid files ready for processing
│     ├── processed/         Files after downstream processing
│     └── rejected/          Empty or invalid files
├── logs/                  Daily log files (auto-generated)
├── scripts/
│     └── run_pipeline.sh    Main automation script
└── README.md

---

## How to Run
Clone the repository:
git clone https://github.com/ahmad2627/data-pipeline-organizer.git

cd data-pipeline-organizer

Update the BASE_DIR path in the script to match your system:
nano scripts/run_pipeline.sh
Change BASE_DIR to your actual path

Add some CSV files to the incoming folder:
echo "id,name,amount" > data/incoming/sales.csv
echo "1,Ahmad,5000" >> data/incoming/sales.csv

Make the script executable and run it:
chmod +x scripts/run_pipeline.sh
./scripts/run_pipeline.sh

---

## Sample Output
[2026-06-17 23:15:37] ============================================
[2026-06-17 23:15:37] Pipeline started by: ahmad2627
[2026-06-17 23:15:37] ============================================
[2026-06-17 23:15:37] All required folders verified.
[2026-06-17 23:15:37] Found 4 CSV file(s) to process.
[2026-06-17 23:15:37] Processing: empty_file.csv (lines: 0)
[2026-06-17 23:15:37] REJECTED: empty_file.csv is empty or has no data rows.
[2026-06-17 23:15:37] Processing: sales_01.csv (lines: 3)
[2026-06-17 23:15:37] MOVED: sales_01.csv → raw/2026-06-17_sales_01.csv
[2026-06-17 23:15:37] Processing: sales_02.csv (lines: 2)
[2026-06-17 23:15:37] MOVED: sales_02.csv → raw/2026-06-17_sales_02.csv
[2026-06-17 23:15:37] Processing: sales_03.csv (lines: 2)
[2026-06-17 23:15:37] MOVED: sales_03.csv → raw/2026-06-17_sales_03.csv
[2026-06-17 23:15:37] ============================================
[2026-06-17 23:15:37] Pipeline Summary for Ahmad:
[2026-06-17 23:15:37]   Total files found:    4
[2026-06-17 23:15:37]   Successfully moved:   3
[2026-06-17 23:15:37]   Rejected (empty):     1
[2026-06-17 23:15:37] ============================================
[2026-06-17 23:15:37] Pipeline completed successfully.

---

## What This Script Demonstrates
- Bash scripting with real-world structure
- Automated file validation and routing
- Timestamp-based file naming
- Logging with timestamps for auditability
- Error handling and safe exit codes
- Production-inspired folder organization
- Core data pipeline concepts (landing → raw → processed)

---

## Concepts Behind This Project
This project reflects real patterns used in data engineering:
**Landing Zone** — raw files arrive in incoming/ without any
processing. This mirrors S3 landing buckets in AWS pipelines.
**Validation Layer** — files are checked before moving forward.
Empty or malformed files are rejected early. This prevents bad
data from entering the pipeline.
**Raw Layer** — valid files land in raw/ with date stamps.
Date stamping enables partitioning and easy debugging later.
**Audit Logging** — every action is logged with a timestamp.
In production, logs are how engineers debug failures at 3am.

---

## Skills Practiced
- Linux terminal and file system navigation
- Bash scripting (variables, loops, conditions, functions)
- File permissions and script execution
- Process management
- Real data pipeline thinking

---

## Part of a Larger Journey
This project is part of my structured Data Engineering roadmap:
- Phase 1 — Industry Foundation ✅
- Phase 2A — Linux and Terminal ✅ (this project)
- Phase 2B — Git and GitHub 🔄 (in progress)
- Phase 2C — Networking Basics
- Phase 3 — Python for Data Engineering
- Phase 4 — SQL and Databases
- Phase 5 — Data Handling with Pandas
- Phase 6 — Core Data Engineering
- Phase 7 — Projects and Portfolio
- Phase 8 — Cloud and Modern Tools
Follow my journey as I build toward my first Data Engineering role.

---

## Author

**Ahmad**
BSIT Student — Building toward a Data Engineering career
GitHub: github.com/ahmad2627
LinkedIn: https://www.linkedin.com/in/muhammad-ahmad-751477369/
