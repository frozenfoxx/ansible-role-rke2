# ansible-role-rke2

Deployment and configuration of RKE2 nodes

# Requirements

None

# Usage

Add to your `requirements.yml`

```yml
roles:
  - name: frozenfoxx.rke2
```

**Scheduler**
```yml
---
- name: Deploy Kubernetes cluster scheduler
  hosts: all
  roles:
    - avahi
    - python
    - frozenfoxx.rke2
  vars:
    rke2_type: "server"
    rke2_channel: "stable"

```

**Worker**
```yml
---
- name: Deploy Kubernetes cluster worker
  hosts: all
  roles:
    - avahi
    - python
    - frozenfoxx.rke2
  vars:
    rke2_type: "agent"
    rke2_channel: "stable"
```

# Contribution

Pull requests welcome.