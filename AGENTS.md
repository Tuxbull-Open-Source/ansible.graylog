# Repository instructions

This repository provides the `tuxbull.graylog` role for the explicitly
authorized Rocky Linux 10 Graylog 7.2 disposable-lab path. Graylog's official
compatibility matrix must be checked before production deployment; this role is
not a production topology reference.

Never commit passwords, password secrets, API tokens, certificates, inventories,
lab logs, or generated files. `graylog_admin_password` must be supplied by
Ansible Vault or an approved secret manager. Preserve `no_log` for secret-bearing
tasks and never print credentials in task output.

Validate YAML, syntax, a fresh disposable-lab convergence, active `mongod`,
`graylog-datanode`, and `graylog-server` services, MongoDB ping, Graylog HTTP
response, and a `changed=0` reconfigure run. Keep release history in
`CHANGELOG.md`, user guidance in `README.md`, and do not self-merge. After merge,
create an immutable SemVer tag and published GitHub Release, then import and
verify the corresponding Galaxy release.
