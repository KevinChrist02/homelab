# Homelab

This is the repo for my homelab. It contains all my selfhosted containers.
But it's important to note, that these are only the docker-compose.yml files and not the
files that contain sensitive data e.g. (.env, /data/)

## Device and Setup

I use the Raspberry Pi 5  with 8Gb of RAM as my homelab device.

![Raspberry Pi](./assets/raspberry_pi.jpg)

Raspberry OS lite is the distro of my choice. The iso is only 500mb large
since the image comes without a desktop environment. This is just fine since
i only SSH into the pi and don't actually need a DE.

For my documents and images i use an external 1TB SSD from crucial.
I mounted the ssd on /mnt/ssd and i route my containers to this exact location.

![SSD](./assets/external_ssd.jpg)

## Tailscale

I don't want to expose my pi with it's ports to the public and deal with all this
port forwarding and certificates.
That's why i chose [Tailscale](https://tailscale.com/). 
Tailscale is as WireGuard-based VPN which creates a mesh-network with my devices (nodes).
One device can access the services of another device by targeting the internal ip, which
was given by tailscale. This enables me to access a service from my pi without exposing 
anything
