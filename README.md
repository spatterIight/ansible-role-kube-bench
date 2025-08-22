# ansible-role-kube-bench

## What it is

An Ansible role to easily facilitate running [kube-bench](https://github.com/aquasecurity/kube-bench) directly on Kubernetes clusters as a job.

## Requirements

- A Kubernetes cluster
- The [kubernetes.core](https://github.com/ansible-collections/kubernetes.core) Ansible collection

## Role Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `kube_bench_version` | See `defaults/main.yml` | The version of kube-bench to run |
| `kube_bench_manifests_to_apply` | `[job.yaml]` | Which kube-bench manifests to apply to the Kubernetes cluster. See the [upstream documentation](https://github.com/aquasecurity/kube-bench/blob/main/docs/running.md#running-in-a-kubernetes-cluster) for more information on why you might want to change this |
| `kube_bench_fail_on_failing_tests` | `true` | Controls whether Ansible should invoke `ansible.builtin.fail` if any kube-bench tests fail |
| `kube_bench_cleanup_pods` | `true` | Controls whether Ansible should delete the completed kube-bench pods |
| `kube_bench_misc_no_log` | `true` | Due to Ansible limitations regarding loops many of the tasks output an incredible amount of text, to resolve this they implement `no_log`. However, if a task has some error this obscures the error. In this case, set this variable to false |

## Testing with Molecule

See [molecule/README.md](molecule/README.md)
