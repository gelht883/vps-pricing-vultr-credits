# Cheap Cloud VPS: What $2.50/Month Really Buys, Why a $3 Plan Can Cost More Than $3, and Where Vultr's $300 Credit Fits (Full Plan Table)

Cheap cloud VPS entry pricing in late 2026 runs from about $2.50 to $11 a month, and the spread has almost nothing to do with hardware quality. Vultr's smallest Cloud Compute instance lists at **$2.50/mo**. InterServer sells a 2 GB KVM slice at **$3/mo** on monthly billing. Hostinger advertises **$6.49/mo**, which requires **$155.76 paid up front for 24 months** and renews at **$11.99/mo**. Liquid Web starts at **$11/mo** for 1 vCPU and 2 GB.

Four prices, four different products, and four different definitions of the word cheap. This piece pulls apart the three numbers that list articles usually blend into one: the sticker price, the first invoice, and the renewal. It also walks through Vultr's $300 new-customer credit, because a promotional balance changes the maths for anyone who wants to test a stack before committing to it.

> **Start here if you want the short version:** Vultr Cloud Compute, Regular Performance, **$2.50/mo** for 1 vCPU / 0.5 GB RAM / 10 GB SSD handles a static site, a reverse proxy or one small container. Step up to High Performance at **$6.00/mo** (1 vCPU / 1 GB / 25 GB NVMe) once you need a full gigabyte and fast disk. New accounts can enter code **FLY300VULTR** for $300 in promotional credit, restricted to new customers and select products, and it cannot be combined with other offers. 👉 [See Vultr's current Cloud Compute pricing](https://www.vultr.com/pricing/?ref=9738262-9J)

## Every Vultr plan line, with entry configuration and price

Vultr's catalogue splits into Cloud Compute (four lines), Optimized Cloud Compute (four lines) and Cloud GPU. The table below shows the entry shape of each line, which is what a first purchase actually looks like. Every line scales well past these configurations, and the GPU line scales to multi-GPU shapes.

| Plan line | vCPU | RAM | Storage | From | Order |
| --- | --- | --- | --- | --- | --- |
| Cloud Compute, Regular Performance | 1 | 0.5 GB | 10 GB | $2.50/mo | [Pick Regular Performance](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J) |
| Cloud Compute, High Performance (AMD) | 1 | 1 GB | 25 GB NVMe | $6.00/mo | [Pick High Performance AMD](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J) |
| Cloud Compute, High Performance (Intel) | 1 | 1 GB | 25 GB NVMe | $6.00/mo | [Pick High Performance Intel](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J) |
| Cloud Compute, High Frequency | 1 | 1 GB | 32 GB NVMe | $6.00/mo | [Pick High Frequency](https://www.vultr.com/products/high-frequency-compute/?ref=9738262-9J) |
| Optimized, General Purpose | 1 | 4 GB | 30 GB NVMe | $30.00/mo | [Pick General Purpose](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized, CPU Optimized | 1 | 2 GB | 25 GB NVMe | $28.00/mo | [Pick CPU Optimized](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized, Memory Optimized | 1 | 8 GB | 50 GB NVMe | $40.00/mo | [Pick Memory Optimized](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Optimized, Storage Optimized | 1 | 8 GB | 150 GB NVMe | $75.00/mo | [Pick Storage Optimized](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud GPU, NVIDIA GH200 | 72 | 480 GB | GPU attached | $2,913/mo, 36-month reserved | [Check Cloud GPU options](https://www.vultr.com/pricing/?ref=9738262-9J) |

Two details change the entry price. The $2.50 Regular Performance figure excludes a dedicated IPv4 address; the same shape lists at **$3.50/mo** with one included, and almost every real deployment needs a public IPv4. Vultr bills on-demand instances hourly with no contract, so a server you destroy stops being a line item. That is the closest thing to a trial you get here, and it matters more than any advertised discount.

## Three billing models, three different meanings of cheap

The gap between a $2.50 headline and a $155.76 invoice is not a pricing trick. It is three separate commercial structures.

**Prepaid multi-year.** Hostinger's KVM 1 at $6.49/mo is priced against a 24-month commitment. The first invoice is $155.76, not $77.88, and the renewal rate for the following term is $11.99/mo. If you stay four years, you pay roughly $443. That is a reasonable deal for a site you know will exist in 2028, and a bad one for a project you might abandon in March.

**Month-to-month slices.** InterServer charges $3/mo for a Linux KVM slice with 2 GB RAM, 30 GB SSD and 2 TB transfer, and lets you add or remove slices as requirements change. Nothing is prepaid, so the annual cost of $36 matches the sticker exactly. The trade-off is that you manage the server yourself with no long-term price protection.

**Hourly on-demand.** Liquid Web prices its $11/mo Cloud VPS at $0.015/hr, and Vultr bills hourly from $2.50/mo upward. You pay for what you run, when you run it. For testing, migration windows or workloads that burst for a week a month, hourly billing is cheaper than any monthly plan. For a server that runs 24/7 for two years, it is not.

When you compare cheap cloud VPS offers, convert everything to the same unit first: **total cash out of your account in the first 30 days**. That single number reorders most shortlists.

## Where the $2.50 tier stops and the $11 tier starts

Across the budget segment, the sub-$5 band reliably means 1 core, 0.5 to 2 GB of RAM and 10 to 60 GB of disk. That ceiling is real, not artificial. It covers:

- A static site or a WordPress install with a caching plugin and modest traffic
- A reverse proxy, VPN endpoint or Tailscale node
- One Docker container doing one job
- A staging box, a scraping job, a cron-driven script

It does not cover MySQL alongside an application, a multi-container Docker Compose stack, or anything running Elasticsearch, Redis with persistence, and a web app on the same box. Those need 2 GB as a floor, and 2 GB is where budget plans start to diverge sharply.

Vultr's ladder is worth reading precisely here. $2.50 buys 0.5 GB. $6.00 buys 1 GB with NVMe. The next rung up the Cloud Compute line is where 2 GB lives, and the Optimized lines open at $28 to $30 for 2 to 4 GB. InterServer's $3 slice already includes 2 GB, which is why it keeps appearing on budget shortlists despite offering less NVMe and a narrower footprint than the large clouds. If your workload needs 2 GB and a database, comparing those two entry points is more useful than comparing marketing pages.

## The add-ons that move the monthly number

The base instance price is rarely the bill. Four line items do the damage.

**IPv4 addresses.** Vultr's $2.50 shape becomes $3.50/mo with a dedicated IPv4. A dollar is trivial in isolation and 40% of the base price in proportion.

**Backups and snapshots.** Hostinger bundles weekly backups free with its US VPS plans. On most clouds, scheduled backups and stored snapshots are billed by volume, and reviewers on G2 single out Vultr's backup pricing as the charge that surprises them. Budget it before you need it.

**Control panels.** cPanel and Plesk are licensed separately from the server on nearly every provider, and a panel licence can exceed the cost of a $6 instance. InterServer lists cPanel and DirectAdmin as optional additions without publishing a price in its VPS table, which is typical.

**Windows.** InterServer's Windows VPS starts at $10/mo rather than $3/mo because Windows Server requires a two-slice minimum, giving 60 GB storage and 4 TB transfer. Some of that gap is RAM and disk, and some is licensing. Any Windows or panel-based deployment needs the full stack priced first, not the Linux entry price. 👉 [Price the full Vultr configuration you actually need](https://www.vultr.com/pricing/?ref=9738262-9J)

## What the $300 credit actually says

Vultr's coupons page lists four current codes. **FLY300VULTR** gives $300 in free credit, **FLYTWOHUNDRED** gives $200, **250VULTRFLY** gives $250, and **VULTRMATCH** matches your first deposit dollar for dollar up to $100.

The restrictions printed on the page apply to all of them: promotional credit applies to select products only, cannot be combined with any other offers, is for new customers only, and further terms and restrictions apply. That means one code per account, not a stack. Pick FLY300VULTR unless you have a specific reason not to, since $300 of credit dominates a $100 deposit match.

Two things to confirm inside your account before you build a plan around the balance. First, which product lines the credit covers, because "select products" is doing real work in that sentence and GPU or bare metal shapes may sit outside it. Second, the expiry window, since promotional balances are time-limited and a credit that lapses in a month is not a 50-month runway on a $6 server no matter how the division looks. The coupons page states the conditions but not the clock, so check the account dashboard rather than a blog post. 👉 [Check Vultr's current credit offers and terms](https://www.vultr.com/coupons/?ref=9738262-9J)

## How the main alternatives compare

| Provider | Entry plan | Configuration | Price and terms | Fits best |
| --- | --- | --- | --- | --- |
| InterServer | KVM Linux VPS | 2 GB RAM, 30 GB SSD, 2 TB transfer | $3/mo, monthly billing, slices can be added or removed | Anyone who needs 2 GB at the lowest possible monthly cost |
| Hostinger | KVM 1 | 1 vCPU, 4 GB RAM, 50 GB NVMe, 4 TB bandwidth | $6.49/mo on a 24-month prepay ($155.76 up front), renews at $11.99/mo | A site you are confident will still be running in two years |
| Liquid Web | Cloud VPS (Compute) | 1 vCPU, 2 GB RAM, 60 GB, 2 TB | $11/mo or $0.015/hr, standard DDoS protection up to 2 Gbps included | Teams that want hourly billing with more infrastructure around the box |
| Vultr | Cloud Compute, Regular Performance | 1 vCPU, 0.5 GB RAM, 10 GB | $2.50/mo ($3.50 with IPv4), billed hourly, no contract | Testing, side projects, and anyone using the $300 credit to learn the platform |

Hostinger gives you the most RAM per dollar if you can commit to 24 months. InterServer gives you the most RAM per dollar with no commitment at all. Liquid Web is the option when support and network protection matter more than the entry price. Vultr's advantage is granularity: nine plan lines, hourly billing and a promotional balance that covers the learning period.

## Deciding in under a minute

Match the workload to the tier and stop shopping:

- **Static site, proxy, single container, learning Linux** → the $2.50 Regular Performance instance. Add the IPv4 and you are at $3.50/mo.
- **WordPress with MySQL, or two to three containers** → 2 GB minimum. InterServer at $3/mo is the cheapest path; Vultr's High Performance line at $6/mo and up buys NVMe and a wider feature set.
- **Managed database, in-memory cache, analytics** → skip the budget tier entirely. Vultr's Memory Optimized line starts at 8 GB for $40/mo because that is what the workload needs.
- **Windows, cPanel or Plesk** → price the licence and the minimum slice count first, then compare. The Linux entry price tells you nothing about the final bill.

Before you enter a card number, confirm three things: whether the promotional credit covers the plan you selected, what the renewal price is after any introductory term, and whether backups are included or metered. Those three answers are the difference between a $36 year and a $155 year.

👉 [Start on Vultr's $2.50 Cloud Compute plan and check the credit terms](https://bit.ly/VuLtr)
