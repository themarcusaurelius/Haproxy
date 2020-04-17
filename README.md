## Collects and parses logs from a (haproxy) process.

When you run this module, it performs a few tasks under the hood:

- Sets the default paths to the log files (but don’t worry, you can override the defaults)
- Makes sure each multiline log event gets sent as a single event
- Uses ingest node to parse and process the log lines, shaping the data into a structure suitable for visualizing in Kibana
- Deploys dashboards for visualizing the log data

### Compatibility

The haproxy module was tested with logs from haproxy running on AWS Linux as a gateway to a cluster of microservices.

This module is not available for Windows.

## Installation

### Linux:

<i>If you haven't already installed filebeat...</i>

1) Enter the following script into the console using elevated privileges

```
curl https://github.com/themarcusaurelius/vizion.ai/blob/master/beat-install-scripts/install-config-haproxy.sh > install-config-haproxy.sh; chmod a+x  install-config-haproxy.sh; ./install-config-haproxy.sh _PLACEHOLDER_API_ENDPOINT_
```

2) When prompted, select the proper environment to complete the installation.

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

<i>If you have already installed filebeat...</i>

1) Enable the module.

```
filebeat modules enable haproxy
```

2) Restart Filebeat.

```
service filebeat restart
```

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

## Example Dashboard

This module comes with a sample dashboard showing geolocation, distribution of requests between backends and frontends, and status codes over time. For example:

![Imgur](https://imgur.com/fQu6k3C.png)
