<div align="center">

<img src="assets/logo-mark.svg" width="88" alt="HotLoop">

# HotLoop

**Automation loops for the real world.**

[Website](https://hotloop.io) &nbsp;·&nbsp; [Docs](https://docs.hotloop.io) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/HotLoop-io/discussions) &nbsp;·&nbsp; [Reddit](https://www.reddit.com/r/HotLoop/) &nbsp;·&nbsp; [Licensing](https://docs.hotloop.io/licensing/) &nbsp;·&nbsp; [Business use, via EmberNET](https://embernet.ai)

</div>

---

## What this actually is

Home automation is a toy right up until the day it matters. Then the cloud is down, the integration broke in last week's update, and your freezer is at 14 degrees with nobody told. Industrial automation has the opposite problem. It works, it costs a fortune, and changing one setpoint means a service call.

HotLoop is the thing in the middle that should have existed ten years ago. It reads real equipment over real protocols, keeps the history, raises the alarm, and moves the machine, from a Pi on a shelf to a whole plant floor. Sense, decide, act, and around again, with nobody babysitting it.

Two things make it worth trusting. It won't lie to you: a sensor it can't read shows up as **bad**, never as zero, so a dead thermocouple doesn't page the night shift about a tank that's fine. And it won't move a machine nobody said it could: every write goes through one gate, writes ship switched off, and every refusal gets written down. The whole point is a loop you can walk away from.

There's no dumbed-down home edition and no enterprise edition holding features hostage. The garage and the plant floor run the same code. Who you are decides how you get it, not what it can do.

## The lineup, and Flow

One codebase, shipped as four products, each with its own image and chart, all released together from one tag. Every one of them speaks every protocol HotLoop has, MQTT included. Features split them, protocols don't, so nobody ever has to run the big one just to reach the PLC on their bench.

| Product | What it is | Status |
|---|---|---|
| **HotLoop IoT** | The automation base, written in Go for OT. Entities, automations, helpers, scripts, the logbook, dashboards, notifications, MCP, and MQTT with discovery for Shelly, ESPHome, Tasmota and Zigbee2MQTT, plus every industrial driver. SQLite or Postgres. | Upcoming. It ships when MQTT discovery works, because an automation base that can't find a smart plug on its own network is a joke. |
| **HotLoop Edge** | IoT plus the machine layer, Ignition Edge style: HMI, PLCs, CODESYS, Pi PLCs, store-and-forward, and an OPC UA server. SQLite, Postgres or TimescaleDB. | Upcoming, alongside IoT. |
| **HotLoop Gateway** | Everything, plus fleet, multi-site and scheduled reports. The site brain. | **4.16.0 is out.** [Install it](https://docs.hotloop.io/gateway/install/). |
| **HotLoop Edge Relay** | Headless. Polls, forwards over Sparkplug B, buffers to disk when the link dies. No database, no UI, nothing to click wrong. | **4.16.0 is out.** [Install it](https://docs.hotloop.io/edge-relay/install/). |

All four are under the [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md), source-available. No license keys, nothing unlocks at runtime, and no dates on IoT and Edge, because a date we miss is worse than none. [hotloop.io/products](https://hotloop.io/products/) has them side by side.

**HotLoop Flow** is its own thing: Node-RED's idea on a runtime that doesn't fall over. One static Go binary, reads your `flows.json` as is, every inbox bounded so one chatty sensor can't OOM-kill the pod, and it won't start without a login. Apache-2.0. Version 2.0.4 is out, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow). It was Emberwire 0.1.0 before it got the name.

## Who gets what for free

**Individual? It's free, whichever one you use.** Your house, your garage, a class you teach, a nonprofit you volunteer for, or because you felt like tinkering at 1am. No trial, no countdown, no upgrade popup six months in.

**Running a business? That depends on the product.** Flow is Apache-2.0: run it, change it, sell it, nobody to ask. The lineup is different. Business use of IoT, Edge, the Gateway or the Edge Relay goes through [EmberNET](https://embernet.ai), whether it's internal only, customer-facing, making you money or saving you money. Signing up for EmberNET is free, and business use of HotLoop there is free. If you want support, SLAs and a warranty, meaning a vendor who picks up the phone instead of a GitHub issue rotting for six months, that's our Official Systems Integrators, [Fireball Industries](https://fireballz.ai).

"Business use" gets fuzzy real fast once somebody starts talking themselves into it, so here's where the line sits for the lineup:

| Situation | Individual, free | Business, through EmberNET |
|---|:---:|:---:|
| Automating your own house | Yes | |
| A hobby project you're building for fun | Yes | |
| A class project or a student lab | Yes | |
| A local nonprofit running it in their own space | Yes | |
| Running it inside a company, internal only, no customers touching it | | Yes |
| Deploying it as part of a product or service you sell | | Yes |
| A landlord automating a rental property they operate as a business | | Yes |
| A contractor installing and managing it for paying clients | | Yes |

Flow has no table like that, because it has no line like that. Apache-2.0 applies to everyone.

Not sure which side you're on? Ask before you build a whole setup on a bad guess. Email support@hotloop.io, or go straight to EmberNET if it smells like a business case. The answer costs you nothing.

The licenses themselves are the legal documents, and they win every argument, including this one. The [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md) covers the lineup and Flow is under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). Everything above is us explaining them like people instead of lawyers. The plain-language version also lives at [docs.hotloop.io/licensing](https://docs.hotloop.io/licensing/).

## Why partners, instead of charging for it ourselves

Building good software and running enterprise support contracts are two different jobs, and a team that pretends to do both ends up mediocre at both. EmberNET is where business use of HotLoop happens. Fireball Industries handles support, SLAs and warranties, the stuff a real company needs before it trusts anything in production. We build the product.

What that buys you: the lineup stays genuinely free and genuinely capable for individuals, and Flow stays open source, instead of everything getting slowly steered toward a paid tier. There's no paid tier to steer toward.

## Where we are right now

**HotLoop Gateway 4.16.0 is out.** It's the first published release since 4.3.1, and it carries everything from 4.4.0 to 4.15.3 in one go. The Edge Relay ships beside it as its own image and chart, same version, and both pull with no login:

```
ghcr.io/hotloop-io/hotloop:4.16.0
ghcr.io/hotloop-io/hotloop-edge-relay:4.16.0
```

The charts are `hotloop` and `hotloop-edge-relay` from `https://hotloop.io/hotloop`, and the Edge Relay has a Quadlet unit for a box outside a cluster. On 4.3.1? Don't just `helm upgrade`. The chart changed its name and Kubernetes won't rename a selector in place, so read [the upgrade](https://docs.hotloop.io/gateway/upgrading/) first or you'll be reading it at 2am anyway. The code lives in this org at `HotLoop-io/hotloop`, and that repo is private for now.

What 4.16.0 gets you: entities, so the plant has names instead of register addresses and everything built from here stands on them. Paging over ntfy, Gotify and Discord, where pressing Acknowledge on your phone acks the alarm in the Gateway. Ignition 8.3.9 reading our OPC UA server end to end, which found two bugs on the way, both fixed. And fixes that matter on a running plant, like a Modbus device with a pulled cable going down in about 11 seconds instead of up to 15 minutes.

Merged since, and landing in the next release:

- **Recipes.** Grade A's setpoints off the laminated sheet and into the plant in one go, checked whole, refused whole, and read back from the device. Nobody fat-fingers the changeover at 2am again.
- **Scripts.** Write the CIP cycle once, run it from a screen, a rule, MCP or its own entity.
- **Blueprints.** Write a rule once with blanks and fill it in per pump. Editing the blueprint on Wednesday doesn't quietly change the rule that was right on Tuesday.
- **Helpers, the logbook, and a real automation language**, so "the pump has been on for five minutes" is one trigger instead of a timer hack.
- **UniFi, read-only.** Switches, ports, PoE and WAN as tags, so a quiet PLC tells you which port it's on. Its very first real read found our own 5G backup link had been dead for two days while the console still called it up.

HotLoop Flow 2.0.4 is out, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow).

Follow [Discussions](https://github.com/orgs/HotLoop-io/discussions) if you want to know the second IoT and Edge ship.

## What lives in this org

| Repo | What it's for |
|---|---|
| `hotloop` | The lineup: IoT, Edge, Gateway and Edge Relay, one codebase. Private for now, so a link would just 404 on you |
| [`hotloop-flow`](https://github.com/HotLoop-io/hotloop-flow) | HotLoop Flow |
| [`HotLoop-io`](https://github.com/HotLoop-io/HotLoop-io) | The HotLoop Community License, the brand standard, and the legal home |
| [`docs`](https://github.com/HotLoop-io/docs) | Source for [docs.hotloop.io](https://docs.hotloop.io) |
| [`HotLoop-io.github.io`](https://github.com/HotLoop-io/HotLoop-io.github.io) | Source for [hotloop.io](https://hotloop.io) |
| [`.github`](https://github.com/HotLoop-io/.github) | Org wide community health files and this homepage |
| [`Discussions`](https://github.com/HotLoop-io/Discussions) | The front door to [org wide Discussions](https://github.com/orgs/HotLoop-io/discussions) |

That last one trips people up, so: Discussions is a GitHub feature that lives at the org level, not inside a repo. The `Discussions` repo holds no conversations. It's a signpost with a README, so anybody scrolling the repo list knows where to click.

## Talk to us

- **Questions, ideas, or just want to talk shop:** [GitHub Discussions](https://github.com/orgs/HotLoop-io/discussions), or [r/HotLoop](https://www.reddit.com/r/HotLoop/) on Reddit
- **Business use of IoT, Edge, the Gateway or the Edge Relay:** [embernet.ai](https://embernet.ai)
- **Official Systems Integrators:** [Fireball Industries](https://fireballz.ai)
- **Found a security problem:** read [SECURITY.md](./SECURITY.md) and email us privately. Don't post it in public, because the first person to read it might not be us
- **Anything else:** support@hotloop.io

## Contributing

[CONTRIBUTING.md](./CONTRIBUTING.md) covers how to get a change in properly. Flow, the website and the docs take pull requests right now. The lineup's repo is private for now, so a bug or an idea for it goes in Discussions, where we'll actually see it.

## Code of Conduct

We follow the [Contributor Covenant](./CODE_OF_CONDUCT.md). Be decent to people. It's not a high bar.
