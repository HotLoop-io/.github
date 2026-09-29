<div align="center">

<img src="assets/logo-mark.svg" width="88" alt="HotLoop">

# HotLoop

**Automation loops for the real world.**

[Website](https://hotloop.io) &nbsp;·&nbsp; [Docs](https://docs.hotloop.io) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/HotLoop-io/discussions) &nbsp;·&nbsp; [Reddit](https://www.reddit.com/r/HotLoop/) &nbsp;·&nbsp; [Licensing](https://docs.hotloop.io/licensing/) &nbsp;·&nbsp; [Business use, via EmberNET](https://embernet.ai)

</div>

---

## What this actually is

Most home automation tools are toys. They are fine until you need them to do something real, and then they fall over. Most industrial automation platforms have the opposite problem: they work, but they cost a fortune and need a whole team to configure. A regular person is never getting near one.

We got tired of that split, so we built HotLoop. It is automation software built around one idea, the loop. Sense what is happening, decide what to do about it, act on that decision, and do it again, indefinitely, without you babysitting it. That loop is the whole point. It is the difference between "I set up a rule once and I hope it still works" and something you can trust to run your house or your equipment while you are not standing there watching it.

The same software runs a single sensor in somebody's garage and a full floor of industrial gear. There is no dumbed-down home edition, and no bloated enterprise edition holding features hostage behind a paywall. Who you are decides how you get it, not what it can do.

## The lineup, and Flow

HotLoop is one codebase shipped as four products, each with its own image and its own chart, all released together from one tag with one version number. Every one of them speaks every protocol HotLoop has, MQTT included. What splits them is features.

| Product | What it is | Status |
|---|---|---|
| **HotLoop IoT** | The automation base, written in Go for OT. Entities, automations, helpers, scripts, the logbook, dashboards, notifications, MCP, and MQTT with discovery for Shelly, ESPHome, Tasmota and Zigbee2MQTT, plus every industrial driver. SQLite or Postgres. | Upcoming release. It ships once MQTT discovery lands. |
| **HotLoop Edge** | IoT plus the machine layer, Ignition Edge style: HMI, PLCs, CODESYS, Pi PLCs, store-and-forward, and an OPC UA server. SQLite, Postgres or TimescaleDB. | Upcoming release, alongside IoT. |
| **HotLoop Gateway** | Everything, plus fleet, multi-site and scheduled reports. SQLite, Postgres or TimescaleDB. | **4.16.0 is out.** [Install it](https://docs.hotloop.io/gateway/install/). |
| **HotLoop Edge Relay** | Headless. Polls, forwards over Sparkplug B, and buffers to disk when the link dies. No database. | **4.16.0 is out.** [Install it](https://docs.hotloop.io/edge-relay/install/). |

All four are under the [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md), source-available. No license keys, nothing unlocks at runtime, and no dates on IoT and Edge, because a date we miss is worse than none. [hotloop.io/products](https://hotloop.io/products/) has the side by side.

**HotLoop Flow** is its own thing: a flow engine in one static Go binary, compatible with Node-RED flow files, under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). Version 2.0.4 is out. 2.0.0 was the first release under the HotLoop Flow name, and it was Emberwire 0.1.0 before that.

## Who gets what for free

**Individual? It is free, whichever one you use.** Run it in your house, your garage, a class you teach, or a nonprofit you volunteer for, or just because you feel like tinkering. No trial, no countdown clock, no upgrade popup waiting for you six months in.

**Running a business? That depends on the product.** HotLoop Flow is Apache-2.0, so a business can run it, modify it, and ship it commercially without asking anyone. The lineup is different. Business use of IoT, Edge, the Gateway or the Edge Relay goes through [EmberNET](https://embernet.ai), and it does not matter whether the use is internal only, customer-facing, making you money, or saving you money. Signing up for EmberNET is free, and business use of HotLoop there is free. When a business wants support, SLAs, and a warranty, meaning a vendor who picks up the phone instead of a GitHub issue sitting untouched for six months, that comes from our Official Systems Integrators, [Fireball Industries](https://fireballz.ai).

A few concrete situations for the lineup, because "business use" gets fuzzy fast once people start talking themselves into it:

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

HotLoop Flow has no such table, because it has no such line. Apache-2.0 applies to everyone.

Genuinely unsure which side of the line you are on? Ask before you build a whole setup on a bad assumption. Email support@hotloop.io, or go straight to EmberNET if it looks like a business case.

The full licenses are the actual legal documents, and they win every argument, including this one. The [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md) covers the lineup, and Flow is under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). Everything above is us explaining them like people instead of lawyers. The plain-language version also lives at [docs.hotloop.io/licensing](https://docs.hotloop.io/licensing/).

## Why partners instead of charging for it ourselves

Building good software and running enterprise support contracts are two different jobs, and pretending one team can do both well is how you end up mediocre at both. EmberNET is where business use of HotLoop happens, and Fireball Industries, our Official Systems Integrators, handle support, SLAs, and warranties, all the things a real company needs before it will trust something in production. We handle the product. Splitting it this way means individuals keep a genuinely free, genuinely capable lineup forever, and Flow stays open source, instead of everything being slowly steered toward a paid tier.

## Where we are right now

**HotLoop Gateway 4.16.0 is out**, the first published release since 4.3.1, with everything from 4.4.0 to 4.15.3 in it at once. So is the Edge Relay, as its own image and chart, same version. Both pull with no login:

```
ghcr.io/hotloop-io/hotloop:4.16.0
ghcr.io/hotloop-io/hotloop-edge-relay:4.16.0
```

The charts are `hotloop` and `hotloop-edge-relay` from `https://hotloop.io/hotloop`, and the Edge Relay has a Quadlet unit for a box outside a cluster. Coming from 4.3.1? It's not a plain `helm upgrade`, so read [the upgrade](https://docs.hotloop.io/gateway/upgrading/) before you touch a running plant. The code lives in this org at `HotLoop-io/hotloop`, and that repo is still private.

What's in 4.16.0: entities, the foundation every automation, helper, script and screen we build from here stands on. Paging over ntfy, Gotify and Discord, where the Acknowledge button on your phone acks the alarm right back into the Gateway. Ignition 8.3.9 reading our OPC UA server, verified end to end. And a pile of fixes that matter on a running plant, like a silent Modbus device that took up to 15 minutes to go down and takes about 11 seconds now.

Merged since, and landing in the next release: helpers, the logbook, the automation language (condition, wait and stop steps, and `forSec` on a state trigger), and scripts, so the CIP cycle gets written once and run from anywhere. Recipes and blueprints are next. A native UniFi integration, built in Go, is in development: Network first, then Protect, Access and PDUs.

HotLoop Flow 2.0.4 is out, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow).

Follow [Discussions](https://github.com/orgs/HotLoop-io/discussions) if you want to know the moment IoT and Edge ship.

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

Quick note on that last one, since it trips people up: Discussions itself is a GitHub feature that lives at the org level, not inside any one repo. The `Discussions` repo doesn't hold the conversations, it's just a signpost with a README explaining what goes there, so anyone landing on the repo list knows where to click.

## Talk to us

- **Questions, ideas, or just want to talk shop:** [GitHub Discussions](https://github.com/orgs/HotLoop-io/discussions), or [r/HotLoop](https://www.reddit.com/r/HotLoop/) on Reddit
- **Business use of IoT, Edge, the Gateway or the Edge Relay:** [embernet.ai](https://embernet.ai)
- **Official Systems Integrators:** [Fireball Industries](https://fireballz.ai)
- **Found a security problem:** read [SECURITY.md](./SECURITY.md) and email us privately, don't post it in public
- **Anything else:** support@hotloop.io

## Contributing

[CONTRIBUTING.md](./CONTRIBUTING.md) covers how to get a change in properly. Flow, the website and the docs take pull requests right now. The Gateway's repo is private for now, so a bug or an idea for it goes in Discussions.

## Code of Conduct

We follow the [Contributor Covenant](./CODE_OF_CONDUCT.md). Be decent to people. It's not a high bar.
