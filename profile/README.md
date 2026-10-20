<div align="center">

<img src="assets/logo-mark.svg" width="88" alt="HotLoop">

# HotLoop

**Automation loops for the real world.**

[Website](https://hotloop.io) &nbsp;·&nbsp; [Docs](https://docs.hotloop.io) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/HotLoop-io/discussions) &nbsp;·&nbsp; [Reddit](https://www.reddit.com/r/HotLoop/) &nbsp;·&nbsp; [License](https://hotloop.io/license/) &nbsp;·&nbsp; [Business use, via EmberNET](https://embernet.ai)

</div>

---

## What this actually is

Home automation is a toy right up until the day it matters. Then the cloud is down, the integration broke in last week's update, and your freezer is at 14 degrees with nobody told. Industrial automation has the opposite problem. It works, it costs a fortune, and changing one setpoint means a service call.

HotLoop is the thing in the middle that should have existed ten years ago. It reads real equipment over real protocols, keeps the history, raises the alarm, and moves the machine, from a Pi on a shelf to a whole plant floor. Sense, decide, act, and around again, with nobody babysitting it.

Two things make it worth trusting. It won't lie to you: a sensor it can't read shows up as **bad**, never as zero, so a dead thermocouple doesn't page the night shift about a tank that's fine. And it won't move a machine nobody said it could: every write goes through one gate, writes ship switched off, and every refusal gets written down. The whole point is a loop you can walk away from.

There's no dumbed-down home edition and no enterprise edition holding features hostage. The garage and the plant floor run the same code. Who you are decides how you get it, not what it can do.

## The lineup, Flow and Cascade

One codebase, shipped as four products, each with its own image and chart, all released together from one tag. Every one of them speaks every protocol HotLoop has, MQTT included. Features split them, protocols don't, so nobody ever has to run the big one just to reach the PLC on their bench. Flow and Cascade are their own products beside them.

| Product | What it is | Status |
|---|---|---|
| **HotLoop IoT** | The automation base, written in Go for OT. Entities, automations, helpers, scripts, the logbook, dashboards, notifications, MCP, and MQTT with discovery for Shelly, ESPHome, Tasmota and Zigbee2MQTT, plus every industrial driver. SQLite or Postgres. | Built and merged. 4.18.5 publishes it, and there is nothing to pull yet. |
| **HotLoop Edge** | IoT plus the machine layer, Ignition Edge style: HMI, PLCs, CODESYS, Pi PLCs, store-and-forward, and an OPC UA server. SQLite, Postgres or TimescaleDB. | Built and merged. 4.18.5 publishes it alongside IoT, and there is nothing to pull yet. |
| **HotLoop Gateway** | Everything, plus fleet, multi-site and scheduled reports. The site brain. | **4.17.0 is out.** [Install it](https://docs.hotloop.io/gateway/install/). |
| **HotLoop Edge Relay** | Headless. Polls, forwards over Sparkplug B, buffers to disk when the link dies. No database, no UI, nothing to click wrong. | **4.17.0 is out.** [Install it](https://docs.hotloop.io/edge-relay/install/). |
| **HotLoop Flow** | Node-RED's idea on a runtime that doesn't fall over. One static Go binary, reads your `flows.json` as is, every inbox bounded so one chatty sensor can't OOM-kill the pod, and it won't start without a login. It was Emberwire 0.1.0 before it got the name. | **2.2.0 is out**, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow). [Install it](https://docs.hotloop.io/flow/install/). |
| **HotLoop Cascade** | The plant talking to everything else. An alarm, a webhook, a schedule or an MQTT burst becomes a batch of items that run through checkpointed steps against real systems, so a dead API or a rebooted box doesn't lose the job. One static Go binary, SQLite or Postgres. | **0.1.2 is out.** The image and chart are public and pull with no login. The source repo is private. [Docs](https://docs.hotloop.io/cascade/overview/). |

All six are under the [HotLoop Business Source License 1.1](https://hotloop.io/license/), Flow from 2.2.0 on. It is source-available, not open source, and I'm not going to dress it up as anything else. No license keys, nothing unlocks at runtime, and no date on a release that hasn't shipped, because a date we miss is worse than none. [hotloop.io/products](https://hotloop.io/products/) has them side by side.

## Who gets what for free

**Home or lab? It's free, whichever one you use.** Your house, your garage, a bench, a class you teach, or because you felt like tinkering at 1am. No trial, no countdown, no upgrade popup six months in. Schools, nonprofits and government bodies are free too, for their own operations and mission, with no sign-up.

**Running a business? That goes through [EmberNET](https://embernet.ai).** Internal only, customer-facing, making you money or saving you money, it's business use all the same. Signing up for EmberNET is free, and business use of HotLoop there is free. If you want support, SLAs and a warranty, meaning a vendor who picks up the phone instead of a GitHub issue rotting for six months, that's our Official Systems Integrator, [Fireball Industries](https://fireballz.ai).

"Business use" gets fuzzy real fast once somebody starts talking themselves into it, so here's where the line sits:

| Situation | Free | Business, through EmberNET |
|---|:---:|:---:|
| Automating your own house | Yes | |
| A hobby project you're building for fun | Yes | |
| A class project or a student lab | Yes | |
| A school, a nonprofit or a government body, for its own mission | Yes | |
| Running it inside a company, internal only, no customers touching it | | Yes |
| Deploying it as part of a product or service you sell | | Yes |
| A landlord automating a rental property they operate as a business | | Yes |
| A contractor installing and managing it for paying clients | | Yes |

What the license does not grant: hosting it as a service for other people, reselling it, and embedding it in something you sell. Each version also turns into GPL-3.0 or later four years after it is first made public, so nothing here stays locked forever.

Not sure which side you're on? Ask before you build a whole setup on a bad guess. Email support@hotloop.io, or go straight to EmberNET if it smells like a business case. The answer costs you nothing.

The [license](https://hotloop.io/license/) is the legal document, and it wins every argument, including this one. The [terms](https://hotloop.io/terms/) cover the rest. Everything above is us explaining them like people instead of lawyers.

## Why partners, instead of charging for it ourselves

Building good software and running enterprise support contracts are two different jobs, and a team that pretends to do both ends up mediocre at both. EmberNET is where business use of HotLoop happens. Fireball Industries handles support, SLAs and warranties, the stuff a real company needs before it trusts anything in production. We build the product.

What that buys you: HotLoop stays genuinely free and genuinely capable for homes, labs, schools, nonprofits and government, instead of everything getting slowly steered toward a paid tier. There's no paid tier to steer toward.

## Where we are right now

**HotLoop Gateway 4.17.0 is out.** The Edge Relay ships beside it as its own image and chart, same version, and both pull with no login:

```
ghcr.io/hotloop-io/hotloop:4.17.0
ghcr.io/hotloop-io/hotloop-edge-relay:4.17.0
```

The charts are `hotloop` and `hotloop-edge-relay` from `https://hotloop.io/hotloop`, and the Edge Relay has a Quadlet unit for a box outside a cluster. On 4.16.0 it's a plain `helm upgrade`, with two catches: use `--reset-then-reuse-values`, not `--reuse-values`, and back up the new `<release>-secret-key` Secret, because the first start encrypts every stored device password with it and from then on that key is part of your data. On 4.3.1 it's not a plain upgrade at all. Either way, read [the upgrade](https://docs.hotloop.io/gateway/upgrading/) first or you'll be reading it at 2am anyway. The code lives in this org at `HotLoop-io/hotloop`, and that repo is private for now.

What 4.17.0 gets you:

- **Recipes.** Grade A's setpoints off the laminated sheet and into the plant in one go, checked whole, refused whole, and read back from the device. Nobody fat-fingers the changeover at 2am again.
- **Scripts.** Write the CIP cycle once, run it from a screen, a rule, MCP or its own entity.
- **Blueprints.** Write a rule once with blanks and fill it in per pump. Editing the blueprint on Wednesday doesn't quietly change the rule that was right on Tuesday.
- **Helpers, the logbook, and a real automation language**, so "the pump has been on for five minutes" is one trigger instead of a timer hack.
- **UniFi, read-only.** Switches, ports, PoE, WAN and clients as tags, so a quiet PLC tells you which port it's on. Its very first real read called our own 5G backup up. It had been dead for two days, and the console's WAN block still said up, which is what HotLoop trusted. The console's health checks knew, so that's what it reads now, and a dead backup reads dead.
- **Device passwords encrypted at rest**, with a key that never sits in the database or a backup.

That sits on 4.16.0's foundation: entities, so the plant has names instead of register addresses, paging over ntfy, Gotify and Discord with an Acknowledge button that actually acks, and Ignition 8.3.9 reading our OPC UA server end to end.

**HotLoop Flow 2.2.0 is out**, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow). Flow talks to the PLCs now (Modbus TCP, OPC UA, S7, EtherNet/IP and Sparkplug B), keeps its context across a restart, and shows you where a message went: click a debug message and the editor lights the path it took. It's also the first Flow under the BSL. 2.1.0 and everything before it keep the license they shipped with. [The release notes](https://hotloop.io/releases/flow/) have the rest.

**HotLoop Cascade 0.1.2 is out.** 0.1.1 was the first Cascade release, and 0.1.2 is the same code built and tested on Podman only. There was a 0.1.0 tag before that, and it never published anything because its chart test failed on a hosted runner. Every step is checkpointed, so a `kill -9` in the middle of a run picks up where it left off. The source repo is private, but the image and the chart are public and pull with no login. [The release notes](https://hotloop.io/releases/cascade/) have the commands.

IoT and Edge are built and merged, 4.18.5 publishes them, and there is nothing to pull yet. Follow [Discussions](https://github.com/orgs/HotLoop-io/discussions) if you want to know the second they ship.

## What lives in this org

| Repo | What it's for |
|---|---|
| `hotloop` | The lineup: IoT, Edge, Gateway and Edge Relay, one codebase. Private for now, so a link would just 404 on you |
| `hotloop-cascade` | HotLoop Cascade. Private for now, so a link would just 404 on you |
| [`hotloop-flow`](https://github.com/HotLoop-io/hotloop-flow) | HotLoop Flow |
| [`HotLoop-io`](https://github.com/HotLoop-io/HotLoop-io) | The HotLoop Business Source License, the brand standard, and the legal home |
| [`docs`](https://github.com/HotLoop-io/docs) | Source for [docs.hotloop.io](https://docs.hotloop.io) |
| [`HotLoop-io.github.io`](https://github.com/HotLoop-io/HotLoop-io.github.io) | Source for [hotloop.io](https://hotloop.io) |
| [`.github`](https://github.com/HotLoop-io/.github) | Org wide community health files and this homepage |
| [`Discussions`](https://github.com/HotLoop-io/Discussions) | The front door to [org wide Discussions](https://github.com/orgs/HotLoop-io/discussions) |

That last one trips people up, so: Discussions is a GitHub feature that lives at the org level, not inside a repo. The `Discussions` repo holds no conversations. It's a signpost with a README, so anybody scrolling the repo list knows where to click.

## Talk to us

- **Questions, ideas, or just want to talk shop:** [GitHub Discussions](https://github.com/orgs/HotLoop-io/discussions), or [r/HotLoop](https://www.reddit.com/r/HotLoop/) on Reddit
- **Business use of any HotLoop product:** [embernet.ai](https://embernet.ai)
- **Official Systems Integrator:** [Fireball Industries](https://fireballz.ai)
- **Found a security problem:** read [SECURITY.md](./SECURITY.md) and email us privately. Don't post it in public, because the first person to read it might not be us
- **Anything else:** support@hotloop.io

## Contributing

[CONTRIBUTING.md](./CONTRIBUTING.md) covers how to get a change in properly. Flow, the website and the docs take pull requests right now. The lineup's repo and Cascade's are private for now, so a bug or an idea for either goes in Discussions, where we'll actually see it.

## Code of Conduct

We follow the [Contributor Covenant](./CODE_OF_CONDUCT.md). Be decent to people. It's not a high bar.
