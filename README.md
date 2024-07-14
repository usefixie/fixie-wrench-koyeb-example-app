fixie-wrench-koyeb-example-app
===============

This is a simple app demonstrating how to use `fixie-wrench`. In this example, HTTP requests to `worldclockapi.com` are proxied though a local port on the Koyeb application instance via `fixie-wrench` and then through Fixie Socks.

The same approach can be used to proxy database connections or any other TCP connection from a static IP address using [Fixie](https://usefixie.com/)

For more information, see the [fixie-wrench documentation](https://github.com/usefixie/fixie-wrench).

## How to use

To get started, [create a Fixie account](https://app.usefixie.com/), and then create a new Proxy Application of **Socks** type.

After the proxy is created, go to Proxy’s Details page where you’ll see a couple of important values:

* **Proxy URL**: Your Fixie HTTP/S or SOCKS proxy URL that includes your username, password and proxy server load-balancer to use.
* **Outbound IPs**: Your pair of Fixie IP-addresses. These will never change, so feel free to allow-list them with firewalls or services

The **Proxy URL** will be needed to power the example below (under `FIXIE_SOCKS_HOST` environment variable).

There are multiple ways to deploy this on Koyeb

### Deploy to Koyeb

Even simpler, using a one button deploy

[![Deploy to Koyeb](https://www.koyeb.com/static/images/deploy/button.svg)](https://app.koyeb.com/deploy?type=git&name=fixie-wrench-koyeb-example-app&repository=github.com/usefixie/fixie-wrench-koyeb-example-app&branch=main&ports=3000;http;/&)

Clicking on this button brings you to the Koyeb App creation page with everything pre-set to launch this application. When presented with the **Deploy on Koyeb** screen to finalize the environment creation, please follow these steps:

* Click **Edit environment variables**
* Set **Name** as `FIXIE_SOCKS_HOST`
* Set **Type** as Secret
* Set **Value** the value of **Proxy URL** from [Fixie's dashboard](https://app.usefixie.com/)

Click **Deploy** when done
