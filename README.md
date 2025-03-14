# Ansible Role: Set System Timezone

An Ansible role to set the system timezone on various Linux distributions, including Red Hat Enterprise Linux 9, AlmaLinux, Rocky Linux, Debian, CentOS, Ubuntu, and many more.

🇩🇪 **Note:** Made with ❤️ in Germany.

## Features

- Easy integration with Foreman/Katello (Import template included)
- Simple and reliable timezone management

## Requirements

- Ansible 2.14 or newer
- Supported Operating Systems: RHEL, AlmaLinux, Rocky Linux, Debian, Ubuntu, CentOS, openSUSE, ArchLinux

## Role Variables

| Parameter                | Required | User Input | Default          | Description                                                          |
|--------------------------|----------|------------|------------------|----------------------------------------------------------------------|
| `n_selected_timezone`    | Yes      | Yes        | `Europe/Berlin`  | Desired system timezone. Example: `Europe/Berlin`, `America/Chicago` |

## Usage

Example usage of this role in an Ansible playbook:

```yaml
---
- hosts: all
  become: true
  roles:
    - role: ansible-role-linux_timezone
      n_selected_timezone: "{{ general_timezone }}"
```

## Foreman/Katello Integration

The Foreman/Katello integration template file is included here:

```
files/ansible-role-linux_timezone.erb
```

You can import this file directly into Foreman:

```
Hosts → Templates → Job Templates
```

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

## Creator

Pierre by NAWKO
