# Uptime Kuma

Uptime Kuma is a self-hosted monitoring tool. It uses to check whether a website, API, server, or other service is available or not.

## What can Monitor?

Uptime Kuma supports several monitor types, including:

- HTTP or HTTPS websites
- TCP ports
- Ping checks
- DNS records
- Docker containers
- Keyword checks

For most beginners, an HTTP monitor is the easiest place to start. It simply requests a URL and checks whether the service responds.

## What a monitor shows

Each monitor keeps a history of checks, called heartbeats. A heartbeat shows whether the check passed or failed, when it happened, and how long the service took to respond.

You can use this information to answer questions such as:
- Is the service currently up?
- When did it last go down?
- How often does it fail?
- Is the response time getting slower?

## Status pages

You can also create a public status page. This is useful when you want to share the current status of a few services without giving people access to your full monitoring dashboard.

## When to use it

Uptime Kuma is a good fit when you need a simple way to monitor availability. It is not a full observability platform, but it works well for uptime checks, basic performance tracking, and alerts.

## Next step

[Install Uptime Kuma](install-uptime-kuma.md)