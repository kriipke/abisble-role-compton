# Ansible Role: Compton Window Compositor

Installs the OS package for the window compositor Compton.
For more information on Compton, see https://github.com/chjj/compton.

Also installs a _system-wide config file_ @ `$XDG_CONFIG_DIRS/compton.conf`, the default config file location for `compton` that sets default transparency for:

- the _active_ window(s)
- _inactive_ windows

## Requirements

- X11
  - Compton is a window manager that operates on windows of the X windowing sysetm. Thus, the basic X11 packages are required to provide the graphical environment for Compton to run in.
- XDG Directories configured
  - Compton's default configuration file will be found at `$XDG_CONFIG_DIRS/compton.conf`. It is recommmended to set these directories in a file such as `/etc/profile/` prior to applying this role.
- `~/.xinitrc`
  - This role also assumes that compton will be launched via `~/.xinitrc`. In order to utilize the configuration file installed by this role add the following to your `~/.xinitrc` startup file: `compton &`

## Role Variables

There are no role variables that configure Compton via Ansible. Instead, the entire configuration file is copied directly from the `Files` subfolder of this role.

## Dependencies

TBD

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kriipke.compton, x: 42 }

## License

BSD

## Author Information

Spencer Smolen `<spencer@xtal.cloud>`
Xtal Systems 2022
