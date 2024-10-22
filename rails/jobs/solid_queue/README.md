## SolidQueue

This role creates a solid_queue worker with systemd job

Variables:

```yaml
solid_queue_job_name: "solid_queue_{{ app_name }}"
solid_queue_config_file: "{{ RAILS_APP_SHARED_PATH }}/config/queue.yml"
```

## Usage:

### 1. Server provisioning

creates the job file

After the userjob / redis:

```yaml
  - role: dresden-weekly.Rails/rails/jobs/solid_queue
```

### 2. Restart after deploy

Somewhere at the beginning of your deployment:

```yaml
  - role: dresden-weekly.rails/rails/jobs/solid_queue/restart
```

At the end of the deployment a complete restart with service handlers is executed.
