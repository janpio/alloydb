# alloydb

[Install CLI](https://cloud.google.com/alloydb/docs/omni/omni-cli):

```
curl https://europe-apt.pkg.dev/doc/repo-signing-key.gpg | sudo apt-key add -
sudo apt update
echo "deb https://europe-apt.pkg.dev/projects/alloydb-omni alloydb-omni-apt main" \
  | sudo tee -a /etc/apt/sources.list.d/artifact-registry.list
sudo apt update
sudo apt-get install alloydb-cli
```

[Install and run database](https://cloud.google.com/alloydb/docs/omni/install):

> Note: Works on GitHub Codespace, but not Gitpod.

```
sudo alloydb system-check
mkdir foo
sudo alloydb database-server install --data-dir=/workspaces/alloydb/foo
sudo alloydb database-server start
```

Currently does not actually work, but fails with:
```
System check passed. Starting AlloyDB Omni...
Configuring memory kernel parameters...
Configuring data directory...
Cleaning old pgtmp-loop and swap files...
Setting up core-dump directory...
Setting up swap file...
Starting memory cleanup...
Removing old data plane containers...
Writing dynamic PostgreSQL parameters...
Resolving data plane images...
Image found locally: gcr.io/alloydb-omni/pg-service:15.2.1
Image found locally: gcr.io/alloydb-omni/memory-agent:15.2.1
Starting AlloyDB Omni containers...
ERROR: error occurred while starting pg-service container: Error response from daemon: path /workspaces/alloydb/foo is mounted on /workspaces but it is not a shared mount
```