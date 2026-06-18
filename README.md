Automated Data Pipeline Organizer
A Bash script that automatically organizes, validates, and logs data pipeline files. Built as a hands-on project during Linux & Terminal fundamentals training.

What It Does
Scans a target directory for incoming data files
Validates file types and basic structure
Organizes files into categorized folders automatically
Logs every action with timestamps
Handles errors gracefully without crashing the pipeline

Skills Demonstrated
Bash scripting
File system navigation and manipulation
Linux permissions and process concepts
Error handling in shell scripts
Logging and automation thinking

Project Structure
pipeline-organizer/
├── organizer.sh          # Main script
├── logs/                 # Auto-generated log files
├── data/
│   ├── incoming/         # Drop files here
│   ├── processed/        # Successfully processed files
│   └── failed/           # Files that failed validation
└── README.md

How to Run
bashchmod +x organizer.sh
./organizer.sh

What I Learned
This project taught me how real data pipelines think about files, not just code. Every file needs validation. Every action needs a log. Every failure needs to be handled, not ignored. These are the same principles used in production Data Engineering pipelines.

Part Of
This project is part of my structured Data Engineering learning roadmap. Phase 2, Section A — Linux and Terminal Foundations.
