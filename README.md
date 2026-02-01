# Genie Spaces Configuration

This repository contains Databricks Genie space configurations managed by **Genie Management Portal**.

## 📁 Structure

```
spaces/
└── {space-name}/
    ├── dev/space.yaml    # Development environment
    └── prod/space.yaml   # Production environment
```

## 🌍 Environments

No environments configured yet.

## 🚀 Workflow

1. **Edit** a space in the portal → creates a branch with dev config
2. **Test** changes using the dev clone
3. **Push to Prod** → creates PR to main
4. **Merge** → GitHub Actions deploys to production

## 🔧 CI/CD

Deployments are handled automatically by GitHub Actions when PRs are merged to main.

## 📝 Local Development

```bash
pip install spaceops

# Validate
spaceops validate spaces/my-space/dev/space.yaml

# Deploy to environment
export DATABRICKS_HOST="https://your-workspace.databricks.com"
export DATABRICKS_TOKEN="dapi..."
spaceops push spaces/my-space/dev/space.yaml
```

---
Managed by [Genie Management Portal](https://github.com/charotAmine/databricks-geniecicd)
