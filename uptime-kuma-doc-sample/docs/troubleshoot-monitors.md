# Troubleshoot monitors

This page covers common issues that may occur when using Uptime Kuma.

## A monitor shows Down

First, check whether the service is actually available.

Open the URL in a browser or run:

```bash
curl -I [https://google.com](https://google.com)
```

If the URL works in your browser but the monitor still shows Down, check the following:

- Is the URL correct?
- Does the service require authentication?
- Is the service only available inside a private network?
- Is Uptime Kuma running in Docker and trying to reach `localhost`?

## Docker and localhost

This is a common issue.

If Uptime Kuma runs inside Docker, `localhost` refers to the container, not your computer. So a monitor pointing to `http://localhost:8080` may fail even if the service is running on your machine.

Use one of these options instead:

- Use your computer’s local IP address.
- Use the Docker network gateway address.
- Use `host.docker.internal` if your Docker setup supports it.

## Too many false alerts

If a monitor goes down for a second and then comes back, you may receive unnecessary alerts.

Try these settings:

- Increase the **Retry** value.
- Increase the **Heartbeat Interval**.
- Use a longer timeout for slow services.

For example, setting retries to `2` means Uptime Kuma will check again before marking the service as down.

## No notifications received

Check these things:

- Is the notification provider configured correctly?
- Did you test the notification?
- Is the notification assigned to the monitor?
- Are notification permissions correct?

It is a good idea to send a test notification before relying on it.

## Slow response times

Slow response times can be caused by:

- A busy server
- Network delays
- A large page or API response
- DNS issues

Check whether the delay happens only for one monitor or for several. If several monitors are slow at the same time, the issue may be with your network or the machine running Uptime Kuma.