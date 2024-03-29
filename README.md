Secure LAN Storage: SSHFS
==
## Installation
See [Secure LAN Storage](https://github.com/phwoolcon/docker-utils/tree/lan-storage)

## Directory structures
The `/data` volume:
```text
/data/
├── depts/
│   └── dev/
├── etc/
│   ├── fstab/
│   │   └── test    -> combine into /etc/fstab
│   │
│   ├── group       -> copy to /etc/ on start
│   ├── passwd      -> copy to /etc/ on start
│   ├── shadow      -> copy to /etc/ on start
│   └── ssh/
│       ├── ssh_host_dsa_key
│       ├── ssh_host_dsa_key.pub
│       ├── ssh_host_ecdsa_key
│       ├── ssh_host_ecdsa_key.pub
│       ├── ssh_host_ed25519_key
│       ├── ssh_host_ed25519_key.pub
│       ├── ssh_host_rsa_key
│       └── ssh_host_rsa_key.pub
├── log/
│   └── sshd.log
├── share/
└── users/
    └── test/
        ├── me/
        └── .ssh/
            └── authorized_keys
```
The `/sshfs` working directory:
```text
/sshfs/
└── test/
    ├── 0-share/    -> bound from /data/share/
    ├── 1-dept/     -> bound from /data/depts/dev/
    └── 2-me/       -> bound from /data/users/test/me/
```
