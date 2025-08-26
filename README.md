# Publishing helm repo into github

## Create a package from helm chart
```heml package <chart-path>```

## Adding the package to index.yaml to prepare helm repo
```helm repo index . --url https://<git-username>.github.io/<git-repo-name> --merge index.yaml```

## Configure github page to host the helm repo into github
1. Navigate to Git Repo → Settings → Pages (or Pages in the sidebar)
2. Make sure the settings look like this:
   - Source: main (or master) branch
   - Folder: / (root)
3. This settings will take fiew minutes to publish the files in the following domain
   - https://<git-username>.github.io/<git-repo-name>

## Verify the published hilm ripo
```helm pull --version <chart-version> --repo https://<git-username>.github.io/<git-repo-name> <chart-name>```
