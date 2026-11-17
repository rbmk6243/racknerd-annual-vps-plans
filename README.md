# RackNerd Specials: What the 5 Annual VPS Plans Cost, Which Tier You Actually Need, and Whether the Renewal Price Holds

The cheapest RackNerd special is the 1 GB KVM VPS at **$21.99 per year**, and the specials page lists exactly five annual plans, ending at 8 GB for $119.99. Most readers should skip the cheapest one and start at the **2 GB plan, $35.99 per year**, because anything with a database, a panel, or two services running at once will not fit comfortably in 1 GB.

Below is what each tier can actually run, what the renewal terms say word for word, what happens if you want your money back, and whether waiting for Black Friday makes sense on November 14.

> **Quick pick**
> - Most people: 2 GB KVM VPS, $35.99/year (2 vCPU, 2 GB RAM, 35 GB SSD, 5 TB transfer)
> - One small job (bot, VPN endpoint, static site, Linux sandbox): 1 GB, $21.99/year
> - Ollama, LibreChat, AnythingLLM, Hermes Agent: 4 GB minimum, $59.99/year
> - OpenClaw: 8 GB, $119.99/year

👉 [See the current specials and lock the $35.99/yr rate](https://bit.ly/RacKnerd)

## All five annual plans, side by side

| Plan | vCPU / RAM / SSD | Monthly transfer | Price per year | Order |
| --- | --- | --- | --- | --- |
| 1 GB KVM VPS | 1 vCPU / 1 GB / 20 GB SSD | 3 TB | $21.99 | [Order the 1 GB plan](https://bit.ly/RacKnerd) |
| 2 GB KVM VPS | 2 vCPU / 2 GB / 35 GB SSD | 5 TB | $35.99 | [Order the 2 GB plan](https://bit.ly/RacKnerd) |
| 4 GB KVM VPS | 3 vCPU / 4 GB / 60 GB SSD | 7 TB | $59.99 | [Order the 4 GB plan](https://bit.ly/RacKnerd) |
| 6 GB KVM VPS | 6 vCPU / 6 GB / 100 GB SSD | 12 TB | $89.99 | [Order the 6 GB plan](https://bit.ly/RacKnerd) |
| 8 GB KVM VPS | 7 vCPU / 8 GB / 150 GB SSD | 20 TB | $119.99 | [Order the 8 GB plan](https://bit.ly/RacKnerd) |

Every plan in that table carries the same baseline: KVM virtualization, full root access, one dedicated IPv4, a 1 Gbps port, deployment in multiple datacenter locations picked at checkout, SSD storage, and provisioning within minutes of payment. RackNerd shows one price per plan, with no struck-through "was" figure and no countdown timer on the page.

The bandwidth numbers scale harder than the RAM does. Moving from the 1 GB plan to the 2 GB plan costs $14 more a year and adds 2 TB of transfer plus a second core. That gap is why the $21.99 box is a poor default: you save $14 once and spend the year watching memory.

## The renewal price is the price you keep

RackNerd answers this directly in its own FAQ: these specials are "lifetime recurring," and you "can renew at the same rate for as long as you decide to keep the service."

That single sentence changes how the numbers should be read. The 2 GB plan at $35.99 works out to roughly $3 a month, and it's still roughly $3 a month in year four, not a promotional $3 that turns into $9 once the first invoice clears. Three years on the 2 GB tier costs $107.97. Three years on the 1 GB tier costs $65.97.

This is also where most of the value in RackNerd specials sits, because the alternative at this price level is usually a monthly plan from a larger cloud whose entry price is temporary or whose bandwidth is metered. If the machine stays up for years, a rate that never moves is worth more than a slightly better spec sheet.

👉 [Check the plan list and start at the rate that stays fixed](https://bit.ly/RacKnerd)

## No refunds by default, so test before you pay

RackNerd's terms are blunt about this. Refunds are handled case by case, and by default none are provided once payment is received. Prepaid account balance is not refundable either. There is no trial window and no money-back period advertised on the specials page.

Disputing the charge instead of asking support is worse. A chargeback triggers an administrative fee reported at **$125 to $250** and can get the account suspended. On a $35.99 order, that's a genuinely bad trade.

The practical consequence: treat the annual payment as final and do your acceptance testing before you choose a datacenter, not after. RackNerd publishes a Looking Glass for each location, plus test IPs and 100 MB / 1 GB test files, so you can pull a file from the exact facility you're considering during your own evening peak. If you've never used the provider and want to see how a location behaves for a few weeks, there is also a separate monthly-billed VPS line you can use to validate the network first, then move to the cheaper annual special once you're satisfied.

Two things worth doing in the first hour after provisioning, while the machine is still new: run a quick disk and CPU benchmark so you know what you actually got, and confirm the out-of-band console loads in your browser. Both take minutes and both are much easier to raise with support on day one than on day ninety.

## Pick the tier by what you'll install, not by RAM alone

RackNerd publishes memory requirements for the one-click apps inside ctrl, and those numbers map cleanly onto the five plans:

| One-click app | Minimum RAM | Plan that fits |
| --- | --- | --- |
| OpenClaw | 8 GB | 8 GB KVM VPS |
| Hermes Agent, AnythingLLM, Ollama, LibreChat | 4 GB | 4 GB KVM VPS (6 GB with headroom) |
| n8n, Coolify | 2 GB, comfortable | 2 GB KVM VPS |
| Docker with Portainer, WordPress via AdminBolt / CyberPanel / CloudPanel | smaller tiers | 1 GB or 2 GB |

The 4 GB plan is the honest entry point for local LLM front-ends, but it's tight once the OS and the app are both resident. If you're actually going to run Ollama with a model loaded and a browser session against it, the 6 GB tier is the one that stops you from tuning swap.

The 6 GB plan is also the odd good deal in the lineup. Going from 4 GB to 6 GB costs **$30 more per year** and doubles the cores from 3 to 6, adds 2 GB of RAM, 40 GB of SSD and 5 TB of transfer. Per core, that's the cheapest step in the whole table. Compiling, container builds, small CI jobs, a handful of services behind a reverse proxy: those workloads get more out of the extra three cores than out of anything else $30 buys here.

👉 [Compare the 6 GB tier against the 4 GB one](https://bit.ly/RacKnerd)

## What you're buying, and what you're not

You get a KVM virtual machine with full root, one IPv4, a 1 Gbps port, and access to **ctrl**, RackNerd's in-house control panel bundled with every special. ctrl handles reboot, OS reinstall, an out-of-band HTML5 VNC console for recovery and custom installs, root password resets, inbound rules through the ctrl Network Firewall, plan upgrades, and the one-click app catalog. There's a public interactive demo of the panel you can click through without an account, which is a faster way to judge whether the tooling suits you than any screenshot.

You do not get a managed server. RackNerd sells these as unmanaged KVM VPS: you get the machine, the panel, and 24/7 support for platform issues, not someone to debug your configs. If you want a host that administers the stack for you, this isn't it.

On the network side, the budget nodes run on older Xeon hardware with ordinary transit, and that shows up in one specific way. Reviews describe slower speeds during Asian evening and weekend peaks. For an audience in Asia, Los Angeles is the commonly recommended location because routes from Chinese ISPs toward LA tend to be the steadiest of the US options. Los Angeles and France are also reported to allow requesting up to 100 free IPv6 addresses. Heavy compilation and latency-sensitive game servers are the two workloads I'd steer elsewhere; everything else that tolerates a shared 1 Gbps port is fine.

OS choice at checkout covers CentOS, Rocky Linux, AlmaLinux, Fedora, Debian and Ubuntu. Anything else goes through a support ticket for a custom ISO, and the HTML5 console lets you install from your own media afterward.

## Buy today or wait for Black Friday 2026?

The 11.11 sale ran November 11 to 13 and has just closed. **Black Friday 2026 runs November 27 to December 2**, and RackNerd treats it as the biggest event of the year, with Cyber Monday deals attached. Historically the calendar has thrown out cheaper entry points than today's: a March Madness sale once listed KVM VPS plans from $14.99 a year. Plan prices rotate, and there's no guarantee today's exact configuration comes back.

My read: if the server is on the critical path this month, buy now. Saving perhaps $10 to $15 by waiting two weeks is a bad trade if the project sits idle in the meantime, and the rate you sign up at is the rate you keep, so a later promo can't be applied retroactively to a plan you already own. If the project is a December or January thing, wait for Black Friday and compare the tiers then; the lineup may shift, and you'll get to see whether a cheaper configuration appears.

Separately, LowEndBox is running a fall giveaway with a November 30 deadline (a Meta Quest 3, a Synology DS225+, two 27-inch monitors, five free-year 4 GB VPS and ten $50 account credits), and no purchase is required to enter.

## How it compares with Hetzner, Contabo and Vultr

| Provider and plan | Entry price | Spec | Where it wins |
| --- | --- | --- | --- |
| RackNerd 2 GB special | $35.99/year | 2 vCPU / 2 GB / 35 GB SSD / 5 TB | Lowest annual cost, fixed renewal rate, large transfer |
| Hetzner CX23 | €5.49/month excl. VAT (about €66/year) | 2 vCPU / 4 GB / 40 GB NVMe / 20 TB | Monthly and hourly flexibility, newer hardware, EU locations, documentation |
| Contabo VPS S | $6.99/month + one-time setup fee | 4 vCPU / 8 GB / 50 GB NVMe / 32 TB | Raw RAM and storage per dollar for self-hosting |
| Vultr entry cloud | $6/month | 1 vCPU / 1 GB / 25 GB SSD / metered | Hourly billing and a large location list for short-lived servers |

Two footnotes on those figures. Hetzner's €5.49 reflects the June 15, 2026 price adjustment that moved the CX23 up from €3.99, which also ended the CAX11's price advantage over Hetzner's own x86 line. Contabo's setup fee is typically about one month's service, and its older oversold CPUs benchmark closer to two modern vCPUs despite the 4 vCPU label.

Nothing mainstream gets near $21.99 a year for a working KVM VPS with a dedicated IPv4 and multi-terabyte transfer. What you give up for it is flexibility and a safety net: an annual commitment, no refund by default, older hardware, and ordinary transit. If any of those three matter more to you than price, Hetzner is the better fit for European workloads and monthly freedom, Contabo for RAM-hungry self-hosting on a fixed monthly bill, Vultr for machines you'll destroy in a week.

## The rule I'd use

Match the box to the job and stop there:
- A bot, a VPN endpoint, a static site, or a throwaway Linux sandbox → 1 GB, $21.99/year
- A database, a web panel, or two or three services at once → 2 GB, $35.99/year
- Anything running a local model or an AI front-end → 4 GB, $59.99/year, or 6 GB, $89.99/year if you want the cores
- OpenClaw → 8 GB, $119.99/year

Before you pay, do two things: pull a test file from the datacenter you're actually choosing, during your own peak hours, and go in accepting that the payment is final. Get those right and the $21.99 to $35.99 range buys a year of a machine most people would otherwise rent monthly at three times the price.

👉 [Pick your tier and deploy in minutes](https://bit.ly/RacKnerd)
