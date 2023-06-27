# Pager Duty

This document discusses the use of PagerDuty for alerting and incident management. The details are specific to the PagerDuty application,
but the general principles apply to whatever product you use.

## Setting up PagerDuty Services

A pattern I've seen, which I now consider an antipattern, is to have multiple PagerDuty services configured for the same application. I've seen
separate Services created for each environment, for different urgency levels, even for different types of errors. This becomes quickly
unmanageable, so I recommend youu **avoid creating multiple PD services for the same application**.

Instead, use the [fields in the Events API](https://developer.pagerduty.com/api-reference/368ae3d938c9e-send-an-event-to-pager-duty#request-body) to indicate
the details of what is impacted, and use the `payload.severity` field to controll the urgency (or, use Event Orchestration to change the urgency).

Here's my recommendatino of how to set the fields:
* `payload.group` - Use this to specify the environment, like "prod", "staging", etc.
* `payload.source` - Use this to specify the specific instance. This might be a hostname, a Nomad allocation ID, a Kubernetes pod ID, etc.

The downside to using a single service is that you can't set a maintenance window for different environments.

