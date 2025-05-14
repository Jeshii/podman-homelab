# podman-homelab
Podman containers for various homelab services.

## Secrets
Be sure to set secrets before running the containers:
```
printf "my_super_secret_password" | podman secret create some-service-secret -
```

## Networking
Allow containers to access lower ports than would normally be possible:
 - Turn it on
    ```
    sudo sysctl net.ipv4.ip_unprivileged_port_start=53
    ```
 - Make it persistent by adding `net.ipv4.ip_unprivileged_port_start=53` to `/etc/sysctl.conf`

## Containers
1. Place the containers in `~/.config/containers/systemd/`
2. Generate services with systemctl --user daemon-reload
3. Start services with `systemctl --user start <service_name>`

