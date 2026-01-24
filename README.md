# SpaceOps CI/CD Example

Full-featured CI/CD for Databricks Genie spaces using [SpaceOps](https://pypi.org/project/spaceops/).

## 📁 Structure

```
dbxsample/
├── .github/workflows/
│   └── deploy.yaml
└── spaces/
    └── billing-analytics/
        ├── dev/space.yaml    # DEV environment
        └── prod/space.yaml   # PROD environment
```

## ✨ Features Included

Each space definition includes:

| Feature | Description |
|---------|-------------|
| **Data Sources** | Tables with column configs |
| **Instructions** | Natural language guidance for Genie |
| **Joins** | Table relationships |
| **Example Queries** | Question + SQL pairs |
| **Filters** | Reusable WHERE clauses |
| **Expressions** | Calculated fields |
| **Measures** | Aggregation snippets |

## 🚀 Setup

### 1. GitHub Secrets

| Secret | Description |
|--------|-------------|
| `DEV_HOST` | DEV workspace URL |
| `DEV_TOKEN` | DEV API token |
| `PROD_HOST` | PROD workspace URL |
| `PROD_TOKEN` | PROD API token |

### 2. Environments

- `dev` - auto-deploy
- `prod` - require approval ✅

### 3. Deploy

```bash
git add spaces/
git commit -m "Update space"
git push
```

## 📝 Local Usage

```bash
pip install spaceops

# Validate
spaceops validate spaces/billing-analytics/dev/space.yaml

# Deploy to DEV
export DATABRICKS_HOST="https://dev.databricks.com"
export DATABRICKS_TOKEN="dapi..."
spaceops push spaces/billing-analytics/dev/space.yaml

# Deploy to PROD
export DATABRICKS_HOST="https://prod.databricks.com"
export DATABRICKS_TOKEN="dapi..."
spaceops push spaces/billing-analytics/prod/space.yaml
```
