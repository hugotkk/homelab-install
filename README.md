apache server to serve config, iso or repo need from netboot

Passwords of those build

- rocky: rocky / rocky
- ubuntu: ubuntu / ubuntu
- xcp-ng: root / xen
- harvester: rancher / rancher

The repo consists solely of the CD, and it's important to include hidden dot files to ensure it functions correctly.

To copy the files in iso
```
mount -o loop xxx.iso /mnt
rsync -avCHcz /mnt/ /var/www/html/xxx/repo/
umount /mnt
```

```bash
tree -L 3 /var/www/html
```

```
.
├── harvester
│   ├── config-create.yaml
│   └── config-join.yaml
├── iso
│   ├── harvester-v1.2.1-amd64.iso
│   ├── openSUSE-Leap-15.0-NET-x86_64-Current.iso
│   ├── Rocky-9.3-x86_64-minimal.iso
│   ├── ubuntu-22.04.3-live-server-amd64.iso
│   ├── xcp-ng-8.3.0-beta1.iso
│   └── xcp-ng-8.3.0-beta1-netinstall.iso
├── README.md
├── rocky
│   ├── ks.cfg
│   └── repo
│       ├── BaseOS
│       ├── EFI
│       ├── images
│       ├── isolinux
│       ├── LICENSE
│       ├── media.repo
│       ├── minimal
│       └── rocky.img
├── ubuntu
│   └── cloud-init
│       ├── meta-data
│       └── user-data
└── xcp-ng
    ├── answerfile.xml
    ├── noresync.sh
    ├── post-install-script
    └── repo
        ├── boot
        ├── EFI
        ├── EULA
        ├── install.img
        ├── LICENSES
        ├── Packages
        ├── repodata
        └── RPM-GPG-KEY-xcpng

```
