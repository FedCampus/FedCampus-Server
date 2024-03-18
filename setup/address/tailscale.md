# How to access server from remote

This document explains how to join and use the FedCampus network using Tailscale. Tailscale is a VPN service that creates a private network of your devices and resources. You can access the fed-ml and fed-iot servers on the network to do tests outside of campus.

## Prerequisites

* You need to have a GitHub account and join the FedCampus GitHub organization.
* You need to install Tailscale on your device. You can download it from https://tailscale.com/download.

## Joining the network

To join the FedCampus network, follow these steps:

1. Open the Tailscale app on your device and sign in with your GitHub account.
2. You will be redirected to a web page where you need to authorize Tailscale to access your GitHub account. Click on "Authorize tailscale".
3. You will see a list of GitHub organizations that you belong to. Select "FedCampus" and click on "Join Network".
4. You will see a confirmation message that you have joined the FedCampus network. Click on "Done".
5. You can now see the FedCampus network on your Tailscale app. You can also see the other devices and resources on the network, such as the fed-ml and fed-iot servers.

## Accessing the resources

To access the resources on the FedCampus network, you can use their Tailscale IP addresses or hostnames. For example, to access the fed-ml server, you can use `100.x.x.x` or `fed-ml.tailc5dce.ts.net`. You can also use any protocols or tools that you normally use, such as SSH, HTTP, RDP, etc.

For example, to SSH into the fed-ml server, you can run:

```bash
ssh user@fed-ml.tailc5dce.ts.net
```

To access the web interface of the fed-iot server, you can open:

```bash
http://fed-iot.tailc5dce.ts.net
```

in your browser.

Do note that there is currently no web interface on either server and there is no plan to do so. For WebUI, please refer to [docker dashbroad](../../docker/usage.md)

## Troubleshooting

If you encounter any issues while using Tailscale, you can check the following:

* Make sure your device is connected to the internet and has Tailscale running.
* Make sure you are signed in with your GitHub account and have joined the FedCampus network.
* Make sure you have permission to access the resource you are trying to reach. You can check the access control lists (ACLs) on the admin console at https://login.tailscale.com/admin/acls.
* If you need further assistance, you can contact the network administrator or visit https://tailscale.com/kb for more documentation and support.
