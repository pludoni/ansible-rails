## Delayed Job

Enables a systemd service job for ``delayed_job`` background worker background worker.

Vars:

```yaml
delayed_job_name: "{{app_name}}_dj"
delayed_job_executable: "bundle_exec rake jobs:work"
delayed_job_user: "{{app_user}}"
delayed_job_workdir: "{{RAILS_APP_CURRENT_PATH}}"
```

## Usage:

### 1. Server provisioning

creates the systemd unit job and enables it

```yaml
  - role: dresden-weekly.Rails/rails/jobs/delayed_job
```

Creates + Enables the systemd unit (service).

### 2. Restart on deploy

```yaml
  - role: dresden-weekly.rails/rails/jobs/delayed_job/restart
```

Restarts the dj at end of deploy.
