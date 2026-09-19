<div align="center">

<img src="assets/logo-mark.svg" width="88" alt="HotLoop">

# HotLoop

**Automation loops for the real world.**

[Website](https://hotloop.io) &nbsp;·&nbsp; [Docs](https://docs.hotloop.io) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/HotLoop-io/discussions) &nbsp;·&nbsp; [Licensing](https://docs.hotloop.io/licensing.html) &nbsp;·&nbsp; [Gateway for business, via Embernet](https://embernet.ai)

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
| Businesses | Through Embernet | Free, no agreement needed |
| Status | Not yet published. The code is moving into this org. | Version 0.1.0 is public today under its original name, Emberwire. The HotLoop Flow release is coming. |

## Who gets what for free

**Individual? It is free, whichever product you use.** Run it in your house, your garage, a class you teach, or a nonprofit you volunteer for, or just because you feel like tinkering. No trial, no countdown clock, no upgrade popup waiting for you six months in.

**Running a business? That depends on the product.** HotLoop Flow is Apache-2.0, so a business can run it, modify it, and ship it commercially without asking anyone. HotLoop Gateway is different. Business use of the Gateway goes through our partner [Embernet](https://embernet.ai), and it does not matter whether the use is internal only, customer-facing, making you money, or saving you money. That is not us crippling the free version to squeeze you later. It is a real partnership, and it means a business gets support, accountability, and a vendor who picks up the phone, instead of a GitHub issue sitting untouched for six months.

A few concrete situations for HotLoop Gateway, because "business use" gets fuzzy fast once people start talking themselves into it:

| Situation | Individual, free | Business, through Embernet |
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

Genuinely unsure which side of the Gateway line you are on? Ask before you build a whole setup on a bad assumption. Email support@hotloop.io, or go straight to Embernet if it looks like a business case.

The full licenses are the actual legal documents, and they win every argument, including this one. The [HotLoop Community License](https://github.com/HotLoop-io/HotLoop-io/blob/main/LICENSE.md) covers the Gateway, and Flow is under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). Everything above is us explaining them like people instead of lawyers. The plain-language version also lives at [docs.hotloop.io/licensing.html](https://docs.hotloop.io/licensing.html).

## Why a partner instead of charging for it ourselves

Building good software and running enterprise support contracts are two different jobs, and pretending one team can do both well is how you end up mediocre at both. Embernet already handles the business side, which is support, SLAs, and procurement, all the things a real company needs before it will trust something in production. We handle the product. Splitting it this way means individuals keep a genuinely free, genuinely capable Gateway forever, and Flow stays open source, instead of everything being slowly steered toward a paid tier.

## Where we are right now

Neither product's code lives in this org yet. HotLoop Gateway is on its way here from a private repository, and HotLoop Flow is on its way from its original home, where it is called Emberwire and where version 0.1.0 is public under Apache-2.0. What you are looking at is the branding, the licensing, the docs, and the community setup, built properly before the code arrives instead of thrown together at the last minute. Follow [Discussions](https://github.com/orgs/HotLoop-io/discussions) if you want to know the moment it lands.

## What lives in this org

| Repo | What it's for |
|---|---|
| [`HotLoop-io`](https://github.com/HotLoop-io/HotLoop-io) | The Gateway license, the brand standard, and the legal home |
| [`docs`](https://github.com/HotLoop-io/docs) | Source for [docs.hotloop.io](https://docs.hotloop.io) |
| [`HotLoop-io.github.io`](https://github.com/HotLoop-io/HotLoop-io.github.io) | Source for [hotloop.io](https://hotloop.io) |
| [`.github`](https://github.com/HotLoop-io/.github) | Org wide community health files and this homepage |
| [`Discussions`](https://github.com/HotLoop-io/Discussions) | The front door to [org wide Discussions](https://github.com/orgs/HotLoop-io/discussions) |

Quick note on that last one, since it trips people up: Discussions itself is a GitHub feature that lives at the org level, not inside any one repo. The `Discussions` repo doesn't hold the conversations, it's just a signpost with a README explaining what goes there, so anyone landing on the repo list knows where to click.

## Talk to us

- **Questions, ideas, or just want to talk shop:** [GitHub Discussions](https://github.com/orgs/HotLoop-io/discussions)
- **Business use of HotLoop Gateway:** [embernet.ai](https://embernet.ai)
- **Found a security problem:** read [SECURITY.md](./SECURITY.md) and email us privately, don't post it in public
- **Anything else:** support@hotloop.io

## Contributing

Once the product actually lands here, [CONTRIBUTING.md](./CONTRIBUTING.md) covers how to get a change in properly. Until then, the website and docs repos take pull requests right now, and if you've got a bug or an idea, Discussions is open today.

## Code of Conduct

We follow the [Contributor Covenant](./CODE_OF_CONDUCT.md). Be decent to people. It's not a high bar.
