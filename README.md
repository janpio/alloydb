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
sudo alloydb database-server install --data-dir=foo
sudo alloydb database-server start
```