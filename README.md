# Ansible Role: Repository checkout

Makes a checkout of the given repository. Will also create given symlinks.

## Requirements

No special requirements.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      vars_files:
        - vars/repository_checkout.yml
      roles:
        - { role: net2grid.repository-checkout }

Inside `vars/repository_checkout.yml`:

    repository_url: "git@bitbucket.org:net2grid/repository-checkout.git"

    checkout_destination: "/path/to/checkout/location"

    config_directory: "/path/to/config/directory/to/create"

    create_symlinks:
      - src: /location/of/existing/file
        dest: /location/of/created/symlink
      - src: /location/of/existing/file2
        dest: /location/of/created/symlink2

## License

MIT / BSD

## Author Information

This role was created in 2017 by NET2GRID BV.
