# 📡 BAKOM Cells Data Collector

This repository automates the monthly retrieval and storage of Swiss mobile network infrastructure data from the Federal Office of Communications (BAKOM).

## 📥 Data Source

The data is sourced from the official BAKOM endpoint:

```
https://data.geo.admin.ch/ch.bakom.standorte-mobilfunkanlagen/standorte-mobilfunkanlagen/standorte-mobilfunkanlagen_2056.json
```

Each dataset provides detailed information about mobile communication installations across Switzerland.

## 🔄 Automation Workflow

The repository utilizes GitHub Actions to automate the following tasks:

- **Scheduled Execution**: Runs on the first day of every month at 00:00 UTC.
- **Manual Trigger**: Can be manually initiated via the GitHub Actions interface.
- **Data Retrieval**: Downloads the latest JSON data from BAKOM.
- **File Naming**: Saves the data with a filename format of `bakom-raw-YYYY-MM-DD.json`.
- **Version Control**: Commits and pushes the new data file to the `data/` directory in the repository.

## 📁 Repository Structure

```
bakom-cells/
├── .github/
│   └── workflows/
│       └── download-bakom.yml  # GitHub Actions workflow file
├── data/
│   └── bakom-raw-YYYY-MM-DD.json  # Monthly data files
└── README.md
```

## ✅ Prerequisites

Ensure the following are set up for seamless operation:

- **GitHub Actions Permissions**: The `GITHUB_TOKEN` must have write permissions to commit and push changes.
- **Branch Protection Rules**: If branch protection is enabled, ensure that GitHub Actions is allowed to push to the branch.

## 🛠️ Customization

To adjust the workflow schedule or data source:

- **Schedule**: Modify the `cron` expression in `.github/workflows/download-bakom.yml`.
- **Data Source URL**: Update the `url` parameter in the workflow file to point to a different data source if needed.

## 📄 License

This project is licensed under the LICENSE
