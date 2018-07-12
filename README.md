# Asible role base server OS configuration (Ubuntu)

## Usage

Add to ansible playbook following:

    - import_role:
        name: dr.server
      vars:
        drs_setup_user: yes
        drs_user: '{{user}}'
        drs_home_dir: /what/you/want/or/not/set/for/default
        drs_pub_key_file: '{{def_user_key_file}}'
        drs_data_dir: '/srv/{{data_dir}}'
      tags: ['os']
      become: yes

params:

- **drs_setup_user:** (yes/no) do setup additional user
- [**drs_user:** (str)] create additional user with sudo
- [**drs_pass:** (str)] new user passwords
- [**def_user_key_file:**] (str) path to public key
- [**drs_data_dir:**] (str) directory outside home that can be used by added user

## Default parameters

Discover in `defaults/main.yml`
