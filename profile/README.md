<div align="center">

<img src="assets/logo-mark.svg" width="88" alt="HotLoop">

# HotLoop

**Automation loops for the real world.**

[Website](https://hotloop.io) &nbsp;·&nbsp; [Docs](https://docs.hotloop.io) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/HotLoop-io/discussions) &nbsp;·&nbsp; [Reddit](https://www.reddit.com/r/HotLoop/) &nbsp;·&nbsp; [Licensing](https://docs.hotloop.io/licensing/) &nbsp;·&nbsp; [Gateway for business, via EmberNET](https://embernet.ai)

</div>

---

## What this actually is

Most home automation tools are toys. They are fine until you need them to do something real, and then they fall over. Most industrial automation platforms have the opposite problem: they work, but they cost a fortune and need a whole team to configure. A regular person is never getting near one.

We got tired of that split, so we built HotLoop. It is automation software built around one idea, the loop. Sense what is happening, decide what to do about it, act on that decision, and do it again, indefinitely, without you babysitting it. That loop is the whole point. It is the difference between "I set up a rule once and I hope it still works" and something you can trust to run your house or your equipment while you are not standing there watching it.

The same software runs a single sensor in somebody's garage and a full floor of industrial gear. There is no dumbed-down home edition, and no bloated enterprise edition holding features hostage behind a paywall. Who you are decides how you get it, not what it can do.

## Two products

HotLoop is two products, and they are licensed differently on purpose.

| | HotLoop Gateway | HotLoop Flow |
|---|---|---|
| What it is | An industrial automation gateway. It speaks seven protocols natively, keeps a history, raises alarms, and runs automations. | A flow engine in one static Go binary, compatible with Node-RED flow files. |
| License | [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md), source-available | [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0), open source |
| Individuals | Free | Free |
| Businesses | Free, through EmberNET | Free, no agreement needed |
| Status | Not yet published. The code lives in this org now, at `HotLoop-io/hotloop`, private for the moment. 4.15.3 is merged and untagged. | Version 2.0.3 is out. 2.0.0 was the first release under the HotLoop Flow name, and it was Emberwire 0.1.0 before that. |

## Who gets what for free

**Individual? It is free, whichever product you use.** Run it in your house, your garage, a class you teach, or a nonprofit you volunteer for, or just because you feel like tinkering. No trial, no countdown clock, no upgrade popup waiting for you six months in.

**Running a business? That depends on the product.** HotLoop Flow is Apache-2.0, so a business can run it, modify it, and ship it commercially without asking anyone. HotLoop Gateway is different. Business use of the Gateway goes through our partner [EmberNET](https://embernet.ai), and it does not matter whether the use is internal only, customer-facing, making you money, or saving you money. Signing up for EmberNET is free, and business use of HotLoop there is free. When a business wants support, SLAs, and a warranty, meaning a vendor who picks up the phone instead of a GitHub issue sitting untouched for six months, that comes from our official systems integrator, [Fireball Industries](https://fireballz.ai).

A few concrete situations for HotLoop Gateway, because "business use" gets fuzzy fast once people start talking themselves into it:

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

Genuinely unsure which side of the Gateway line you are on? Ask before you build a whole setup on a bad assumption. Email support@hotloop.io, or go straight to EmberNET if it looks like a business case.

The full licenses are the actual legal documents, and they win every argument, including this one. The [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md) covers the Gateway, and Flow is under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). Everything above is us explaining them like people instead of lawyers. The plain-language version also lives at [docs.hotloop.io/licensing.html](https://docs.hotloop.io/licensing.html).

## Why partners instead of charging for it ourselves

Building good software and running enterprise support contracts are two different jobs, and pretending one team can do both well is how you end up mediocre at both. EmberNET is where business use of HotLoop happens, and Fireball Industries, our official systems integrator, handles support, SLAs, and warranties, all the things a real company needs before it will trust something in production. We handle the product. Splitting it this way means individuals keep a genuinely free, genuinely capable Gateway forever, and Flow stays open source, instead of everything being slowly steered toward a paid tier.

## Where we are right now

HotLoop Flow 2.0.3 is out, at [HotLoop-io/hotloop-flow](https://github.com/HotLoop-io/hotloop-flow). 2.0.0 was the first release under this name, and before that it was published as Emberwire 0.1.0. HotLoop Gateway made the move too. The code is in this org at `HotLoop-io/hotloop`, and the repo is private for now. It's at 4.15.3 on paper, with everything since 4.3.1 merged and none of it tagged, and the [release notes](https://hotloop.io/releases/gateway/) say exactly that instead of pretending otherwise.

What's landed lately: the OPC UA driver logs in to secured servers and is verified against Ignition 8.3.9, which promptly found us a bug. Device credentials are hidden from every role, for every protocol. There are scheduled reports, and paging over ntfy, Gotify and Discord, where the Acknowledge button on your phone acks the alarm right back into the Gateway. Discord hasn't been pointed at the real Discord yet, and the docs say so. And there are entities, which is the start of the real plan: everything Home Assistant does that a factory actually wants, rebuilt in Go for the plant floor. Follow [Discussions](https://github.com/orgs/HotLoop-io/discussions) if you want to know the moment it ships.

## What lives in this org

| Repo | What it's for |
|---|---|
| `hotloop` | HotLoop Gateway and the Edge Relay. Private for now, so a link would just 404 on you |
| [`hotloop-flow`](https://github.com/HotLoop-io/hotloop-flow) | HotLoop Flow |
| [`HotLoop-io`](https://github.com/HotLoop-io/HotLoop-io) | The Gateway license, the brand standard, and the legal home |
| [`docs`](https://github.com/HotLoop-io/docs) | Source for [docs.hotloop.io](https://docs.hotloop.io) |
| [`HotLoop-io.github.io`](https://github.com/HotLoop-io/HotLoop-io.github.io) | Source for [hotloop.io](https://hotloop.io) |
| [`.github`](https://github.com/HotLoop-io/.github) | Org wide community health files and this homepage |
| [`Discussions`](https://github.com/HotLoop-io/Discussions) | The front door to [org wide Discussions](https://github.com/orgs/HotLoop-io/discussions) |

Quick note on that last one, since it trips people up: Discussions itself is a GitHub feature that lives at the org level, not inside any one repo. The `Discussions` repo doesn't hold the conversations, it's just a signpost with a README explaining what goes there, so anyone landing on the repo list knows where to click.

## Talk to us

- **Questions, ideas, or just want to talk shop:** [GitHub Discussions](https://github.com/orgs/HotLoop-io/discussions), or [r/HotLoop](https://www.reddit.com/r/HotLoop/) on Reddit
- **Business use of HotLoop Gateway:** [embernet.ai](https://embernet.ai)
- **Official Systems Integrators:** [Fireball Industries](https://fireballz.ai)
- **Found a security problem:** read [SECURITY.md](./SECURITY.md) and email us privately, don't post it in public
- **Anything else:** support@hotloop.io

## Contributing

[CONTRIBUTING.md](./CONTRIBUTING.md) covers how to get a change in properly. Flow, the website and the docs take pull requests right now. The Gateway's repo is private for now, so a bug or an idea for it goes in Discussions.

## Code of Conduct

We follow the [Contributor Covenant](./CODE_OF_CONDUCT.md). Be decent to people. It's not a high bar.
