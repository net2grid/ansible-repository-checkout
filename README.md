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

    repositories:
      - url: "git@github.com:somebody/some-repository.git"
        destination: "/some/directory"
      - url: "git@github.com:somebody/some-other-repository.git"
        destination: "/some/other-directory"
        branch: a_branch_name
    
    create_directories:
      - "/a/directory-that-needs-to-be-created"
      - "/a/second-directory-that-needs-to-be-created"
    
    composer_install:
      - "/some/directory"
    
    create_symlinks:
      - src: /some/dir/config.ini
        dest: /some/other-directory/config.ini

    writeable_dirs:
      - "some/directory/cache/"
      - "some/directory/logs/"

## License

MIT / BSD

## Author Information

This role was created in 2017 by NET2GRID BV.
