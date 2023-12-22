# cci-local-cli
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/mfunaki-circleci/local-cli/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/mfunaki-circleci/local-cli/tree/main)

Taken from [WindowsでCircleCIのローカル環境を動かす](https://ancozerticht.hatenablog.com/entry/2022/08/27/212337).

```
circleci config validate
circleci local execute build
```

If you see an error like this,

```
Error: 
Unexpected environment preparation error: Error response from daemon: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: unable to apply cgroup configuration: cannot enter cgroupv2 "/sys/fs/cgroup/docker/06cde53c90d3f18839155790414d54f3e2f1d0696bf185fb9c10f67bb767caf5/0bd643378bd12aa320a826d6c50f9de5d846278e3cdaae91ec70b1e25f51c4c7" with domain controllers -- it is in an invalid state: unknown

Step failed
Task failed
```

this can be solved by changing `deprecatedCgroupv1` to be true in `~/Library/Group Containers/group.com.docker/settings.json'` (suggested in https://github.com/ktr11/booster/issues/36).