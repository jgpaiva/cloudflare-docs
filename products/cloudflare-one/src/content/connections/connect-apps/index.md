---
order: 0
pcx-content-type: concept
---

# Connect resources

Cloudflare Tunnel provides you with a secure way to connect your resources to Cloudflare without a publicly routable IP address. With Tunnel, you do not send traffic to an external IP — instead, a lightweight daemon in your infrastructure (`cloudflared`) creates outbound-only connections to Cloudflare’s edge. Cloudflare Tunnel can connect HTTP web servers, [SSH servers](/tutorials/ssh), [remote desktops](/tutorials/rdp), and other protocols safely to Cloudflare. This way, your origins can serve traffic through Cloudflare without being vulnerable to attacks that bypass Cloudflare.

## How it works

Cloudflared establishes outbound connections (tunnels) between your resources and the Cloudflare edge. Tunnels are persistent objects that route traffic to DNS records. Within the same tunnel, you can run as many `cloudflared` processes (connectors) as needed. These processes will establish connections to the Cloudflare edge and send traffic to the nearest Cloudflare data center.

![Tunnel Diagram](../../static/documentation/connections/connect-apps/handshake.jpg)

## Working with Cloudflare Tunnel

Most interactions with Cloudflare Tunnel require the use of a CLI — for example, creating and configuring tunnels, and running a tunnel or routing traffic through it. To get started, visit the [Cloudflare for Teams Dashboard](https://dash.teams.cloudflare.com) and navigate to **Access** > **Tunnels**. When visiting the page for the first time, a step-by-step tutorial will help you create your first tunnel.

Once your first tunnel is connected to Cloudflare, use this page to check your [tunnel status](#tunnel-status) and view a comprehensive list of active or inactive tunnels. You’ll also be able to filter tunnels by name, status, uptime, or creation date, and use the search bar to retrieve tunnels by name.  

![Tunnel UI](../../static/documentation/connections/connect-apps/tunnel-blog.png)

### Tunnel status

A tunnel's status depends on the health of its connections:

* **Active**: This means your tunnel is running and has a healthy connection to the Cloudflare Network.
* **Inactive**: This means your tunnel is not running and is not connected to Cloudflare.
* **Degraded**: This means one or more of your four long-lived TCP connections to Cloudflare have been disconnected, but traffic is still being served to your origin.

## Getting started

Follow our [step-by-step guide](/connections/connect-apps/install-and-setup/tunnel-guide) on how to get your first tunnel up and running. The guide covers how to download, install and authenticate `cloudflared`, create your first tunnel, route traffic through it, and ultimately run your tunnel.

You can familiarize yourself with Cloudflare Tunnel concepts and terminology by checking out the [Useful Terms page](/connections/connect-apps/install-and-setup/tunnel-useful-terms). For a list of common tunnel commands, refer to the [Useful Commands page](/connections/connect-apps/install-and-setup/tunnel-useful-commands).
