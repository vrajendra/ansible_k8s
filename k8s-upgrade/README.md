# Kubernetes HA Rolling Upgrade Ansible

## Features

- First control plane upgrade with automatic rollback
- Remaining control planes upgraded serially
- Workers upgraded in batches of 5
- Etcd snapshot before upgrade
- Preflight checks (maintenance window, node health)
- Handles pinned pods safely
- Optional rollback for worker batch failures
- Works in lab (1 CP + 2 workers) or production (3 CP + 50 workers)

## Inventory

Example: `inventory/hosts.ini`

```ini
[kube_control_plane]
cp1
cp2
cp3

[kube_workers]
worker1
worker2
worker3
...