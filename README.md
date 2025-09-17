# 40docs Workshop Local Development Setup

Quick setup script for local MkDocs development of 40docs workshop documentation.

## Requirements

- Python 3.9+ (stable, not beta)
- Git
- **macOS**: Xcode Command Line Tools
- **Linux**: build-essential

## Quick Start

```bash
# Run setup with any workshop_* repository
./setup_local_mkdocs.sh workshop_azure

# Start server
cd workshop_azure-playground
source ../venv/bin/activate
mkdocs serve
```

Access at http://localhost:8000

## Usage

### Update Content
```bash
cd workshop_azure-playground
git pull origin main
```

### Multiple Workshops
Same virtual environment works for all workshops:
```bash
./setup_local_mkdocs.sh workshop_aws
cd workshop_aws-playground
source ../venv/bin/activate
mkdocs serve
```

## Structure

```
.
├── setup_local_mkdocs.sh
├── venv/
└── workshop_*-playground/
    ├── mkdocs.yml
    ├── theme/
    └── docs/
```

## Compatible Repositories

Any 40docs repository prefixed with `workshop_`:
- `workshop_azure`
- `workshop_aws`
- `workshop_gcp`
- `workshop_*`

## Troubleshooting

**Python issues**: Install Python 3.9+ stable
**Build errors**: Install Xcode (macOS) or build-essential (Linux)
**Port conflict**: Use `mkdocs serve -a localhost:8001`