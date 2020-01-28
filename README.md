Minecraft
=========

An Ansible role for installing / starting minecraft on RHEL/CentOS 7 server with backup cron.

Requirements
------------

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook with `become: yes`.

**NOTE:** Use of this playbook acknowledges and accepts the terms of [Minecraft's EULA](https://account.mojang.com/documents/minecraft_eula).

Role Variables
--------------

Ansible variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
mc_root: /opt/minecraft
max_memory: 2048M
min_memory: 512M

view_distance: 10
game_mode: creative
port: 25565
allow_nether: "true"
command_block: "false"
allow_rcon: "false"
level_name: world
motd: "Welcome to Minecraft!"
player_idle_timeout: 0
online_mode: "true"
allow_flight: "false"
force_gamemode: "false"
hardcore: "false"
pvp: "false"
max_players: 10
difficulty: easy
```

The `mc_update` boolean variable determines whether the role will fetch and install the latest server JAR, if one is already installed.

```yaml
mc_update: False
```

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: mc-servers
  become: yes
  tasks:
  - include_role:
      name: minecraft
    vars:
      motd: "My Minecraft Server"
      max_players: 12
      pvp: "true"
```

License
-------

BSD

Author Information
------------------

Written by Chad Geary. Converted to a role by Sean Callaway.
