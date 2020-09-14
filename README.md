# Check Required Variables
Ansible role that checks that required variables are defined.

## Requirements
None.

## Role Variables
Available variables are listed below, along with default values `(see defaults/main.yml)`:
```yaml
required_vars: {}
```
Pass the variable to check to `required_vars`:
```yaml
required_vars:
  var1_name: "{{ var1_name }}"
  var2_name: "{{ var2_name }}"
```
Add `no_log` option for `silent_vars`:
```yaml
silent_vars:
  - "var1_name"
```

## Dependencies
None.

# Example Playbook
```yaml
- name: Check required variables
  hosts: all
  become: true
  roles:
    - role: check-required-variables
      required_vars:
        required: "{{ required }}"
```

## Test
### Requirements
- python >= 3.7
- docker

### Run
```bash
pip install -r requirements.txt
molecule test
```

## License
MIT
