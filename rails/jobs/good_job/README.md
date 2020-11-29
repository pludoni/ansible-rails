## GooJob

This role creates a good_job worker with systemd job

Variables:

```yaml
good_job_job_name: "good_job-{{ app_name }}"
good_job_rails_env: "{{ rails_env }}"
good_job_log_file: "{{ RAILS_APP_SHARED_PATH }}/log/good_job.log"
good_job_config_file: "{{ RAILS_APP_SHARED_PATH }}/config/good_job.yml"
good_job_configuration_max_threads: 5
```

## Usage:

### 1. Server provisioning

creates the job file

After the userjob / redis:

```yaml
  - role: dresden-weekly.Rails/rails/jobs/good_job
```

### 2. Restart after deploy

Somewhere at the beginning of your deployment:

```yaml
  - role: dresden-weekly.rails/rails/jobs/good_job/restart
```

At the end of the deployment a complete restart with service handlers is executed.
