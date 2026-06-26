# 06 – Competitive Landscape
**Status:** COMPLETE
**Owner:** Founder
**Last Updated:** 2026-06-24
**Document Version:** 1.0
**Constitutional Traceability:** Doctrine §I (property is primary entity), Doctrine §III
(we assemble records, not create knowledge), Doctrine §IX (infrastructure not product),
Missing Memory Layer §10 (why existing solutions do not provide a persistent institutional record)

---

## The Central Framing Challenge

Haus Registry does not fit neatly into any existing competitive category. It is not
a listing platform. It is not a home management app. It is not a property data
aggregator. It is not a contractor marketplace. It is not an inspection company.

This means the competitive landscape cannot be analyzed as a straightforward
market share exercise. The right question is not "who are we competing with for
the same customers?" The right question is: **who occupies adjacent territory,
what problem are they solving, why does their solution not address the market
failure we exist to solve, and what is the realistic competitive risk?**

The Missing Memory Layer (Document 02) established that no existing solution
provides a persistent institutional record that belongs to the property across
its entire lifecycle. This document substantiates that finding by analyzing the
specific categories of adjacent solutions — their purpose, their limitations,
and their relationship to Haus Registry.

It also names the real competitive risks: not the companies that are building
what we are building, but the forces that could prevent the category from
emerging on our terms.

---

## Category 1: Home Management Applications

### Who They Are

A cluster of consumer applications designed to help homeowners organize home-related
information. The category includes HomeZada, HomeBinder, Homer (which absorbed
the Centriq user base when Centriq shut down January 31, 2026), DomiDocs, ZYYAH,
and Real Estate Ledger, among others.

### What They Solve

These applications solve a personal organization problem. They help individual
homeowners maintain records of their appliances, maintenance schedules, warranties,
and improvement projects in a digital format that is more accessible than a filing
cabinet.

HomeZada is the most established platform in this category, having launched in
2012. It covers home inventory, maintenance scheduling, project budgeting, financial
dashboards, and AI-assisted home management. Pricing runs $59–189 per year.

HomeBinder is distributed through real estate agents and home inspectors at closing,
giving it a transaction-adjacent distribution advantage. It is free at the base tier.

Homer absorbed Centriq's user base following Centriq's January 2026 shutdown —
a significant event in itself. Centriq had accumulated years of homeowner appliance
data; when the company closed, users who had not exported their data lost it
permanently. This event illustrates precisely the structural limitation of
owner-centric, platform-dependent record storage.

Real Estate Ledger is an emerging entrant positioning around verified, shareable
property documentation with blockchain-backed document fingerprinting — the
closest adjacent product to what Haus Registry is building, though still
fundamentally owner-centric.

### Why They Do Not Solve the Market Failure

Every home management application in this category shares a defining structural
limitation: **the record belongs to the owner's account, not the property.**

When the homeowner sells the house, the record stays with the user account.
The buyer starts over. The institutional memory of the property — the accumulated
maintenance history, appliance records, contractor relationships, permit copies —
does not transfer.

This is not a product execution failure. It is a category design choice. These
applications are built to serve homeowners. They are not built to serve properties.
The data model is organized around the user, not the Registry ID. As a consequence,
they reproduce the market failure at the moment of ownership transition — precisely
the moment when the record would be most valuable.

A second structural limitation: these applications rely entirely on homeowner data
entry. There is no mechanism for contractor verification, municipal permit
integration, insurance record connection, or manufacturer warranty registration.
The record is as complete as the homeowner's diligence. For most homeowners, this
means the record is partial, inconsistent, and unverifiable.

Centriq's January 2026 shutdown is the most instructive data point in this category.
Years of homeowner-entered appliance data was permanently deleted when a single
company made a business decision to close its product. An infrastructure company
that treats property records as platform data — rather than as records belonging
to the property — is fragile by design. Haus Registry is architecturally required
to be the opposite: records belong to the property, survive platform changes, and
accumulate across every ownership cycle.

### Relationship to Haus Registry

These are not competitors in the traditional sense. They are solving a different
problem for a different purpose. A homeowner who uses HomeZada is better organized
than one who doesn't — but they are still not building a persistent institutional
record that will survive their ownership and serve the next buyer, the next lender,
and the next insurer.

The home management app category does, however, demonstrate real consumer demand
for home organization tools. This is a positive market signal. It means homeowners
will engage with digital home management — they need the right product, not
proof of the need.

The risk: if a well-capitalized home management platform makes the architectural
shift to property-centric, transferable records before Haus Registry establishes
the category, the distribution advantage of an existing user base could matter.
This is the category's primary competitive threat, not its current state.

---

## Category 2: Property Data Aggregators

### Who They Are

Companies that aggregate property data from public records, MLS systems, and
other sources to provide analytics, valuations, and market intelligence to
institutional clients. The primary players are CoreLogic (rebranded as Cotality
in 2025), ATTOM Data Solutions, Zillow, and CoStar.

### What They Solve

These companies solve a market analytics and valuation problem. They aggregate
historical sales data, public records (assessor data, deed transfers, tax records,
permit filings where available), and market condition data to enable institutional
decision-making — mortgage underwriting, insurance pricing, appraisal support,
investment analysis.

CoreLogic (Cotality) covers 99.9% of US properties and is the primary data
supplier to mortgage lenders, insurers, and government agencies requiring
property information at scale. In 2024, CoreLogic launched Araya, an AI-powered
platform designed to provide property, portfolio, and market insights to real
estate professionals.

ATTOM Data covers over 158 million US residential and commercial properties,
providing tax records, deed information, mortgage data, foreclosure records,
environmental risk data, and neighborhood data via API.

Zillow aggregates MLS data and public records for consumer-facing property
discovery, price estimation, and market research.

### Why They Do Not Solve the Market Failure

Property data aggregators are organized around **transaction and valuation history**,
not property lifecycle history. Their data model answers questions about ownership
transfers, price trends, and market conditions. It does not answer questions about
what has been maintained, repaired, replaced, or improved within a property across
its physical lifecycle.

CoreLogic's coverage of 99.9% of US properties is authoritative within its scope:
ownership records, assessed values, sales history, permit filings where available.
It does not include the contractor-verified maintenance records, warranty
registrations, inspection reports, or equipment histories that constitute the
persistent institutional record Haus Registry is building.

The data these companies hold is primarily backward-looking (what happened in
transactions) and public-record-sourced (what governments have recorded). It is
not forward-looking (what maintenance is due) and it is not lifecycle-complete
(what has happened to the physical property between transactions).

Crucially, property data aggregators are **institution-centric by design** — they
sell data to the institutions that pay for it (lenders, insurers, appraisers),
not to the property or to the homeowner. The property is a reference object in
their databases, not the primary entity. This is the same architectural limitation
that characterizes every existing system documented in the Missing Memory Layer.

### Relationship to Haus Registry

Property data aggregators are the companies most likely to eventually want to
**acquire or integrate** Haus Registry rather than compete with it directly. The
lifecycle data we assemble — verified maintenance history, improvement records,
warranty status, contractor records — is precisely the layer of data missing from
CoreLogic, ATTOM, and similar platforms.

In the near term, they are potential data partners (we can enrich our Registry
with their public record feeds) and eventual distribution channels (lenders and
insurers who already rely on CoreLogic could access Registry data through their
existing data stack).

The competitive risk is different here: if CoreLogic or a well-capitalized
equivalent decides to build the lifecycle record layer organically, their existing
institutional relationships and property coverage give them significant distribution
advantages. The moat against this is speed, data accumulation, and the network
effects of a property-centric record that grows with every contribution from
homeowners, contractors, and professionals.

---

## Category 3: Real Estate Transaction Platforms

### Who They Are

MLS systems, listing portals (Zillow, Redfin, Realtor.com), transaction management
platforms, and title companies. These are the systems that facilitate the buying
and selling of residential properties.

### What They Solve

Transaction platforms solve the matching and facilitation problem: connecting
buyers with sellers, managing the documentation of legal ownership transfer,
and in the case of title companies, verifying the legal chain of ownership and
clearing encumbrances.

### Why They Do Not Solve the Market Failure

Transaction platforms are explicitly designed around the transaction event, not
the property lifecycle. A listing is created when a property enters the market.
It is archived when the property sells. The data generated — photographs, listing
descriptions, sale price, days on market — is transactional metadata. It is not
a persistent property record.

Title companies preserve the legal memory of a property with precision: who has
owned it, what liens exist, whether the chain of title is clean. They do not
preserve the physical memory of the property: what was maintained, what was
repaired, what was improved.

The MLS and listing portal ecosystem is organized around the agent relationship
and the listing event. It has no architectural capacity — and no business incentive
— to maintain records between transactions.

### Relationship to Haus Registry

Transaction platforms are **distribution channels**, not competitors. The moment
of transaction is when the Registry Report is most valuable — to buyers, sellers,
agents, lenders, and title companies simultaneously. Registry Pro can serve agents
and inspectors who participate in transactions. Registry Reports can become a
standard component of the closing package.

The competitive risk here is primarily one of distribution: if a major transaction
platform (Zillow, Redfin) decided to build a property history product, their
existing consumer distribution would give them significant reach. The moat is
the quality and depth of the Registry itself — a Registry assembled from
homeowner, contractor, professional, and government sources over years of
continuous ownership is more valuable than any transaction-triggered snapshot.

---

## Category 4: Contractor and Service Marketplaces

### Who They Are

Platforms connecting homeowners with home service professionals. The major players
are Angi (formerly Angie's List), Thumbtack, TaskRabbit, and HomeAdvisor. These
are marketplace businesses — they earn revenue from contractor lead generation
and homeowner service bookings.

### What They Solve

Contractor marketplaces solve the discovery and matching problem: helping homeowners
find qualified professionals for specific jobs, and helping contractors find
customers. Some platforms include review systems, project tracking, and payment
processing.

### Why They Do Not Solve the Market Failure

Contractor marketplaces are organized around the service transaction, not the
property record. When a homeowner books a plumber through Angi, the service
event may be recorded in the platform — but the record belongs to the
homeowner's Angi account, it is not attached to the property, it is not verifiable
by a subsequent owner, and it does not persist in any form that serves future
participants in the property's lifecycle.

These platforms optimize for transaction volume and contractor-homeowner matching.
The record of what was done is incidental to their business model — a feature that
supports review writing, not a product in itself.

### Relationship to Haus Registry

Contractor marketplaces are **Registry Network participants**, not competitors.
A contractor who completes a job through Angi could also submit a verified work
record to the Property Registry through Registry Pro. The Angi transaction and
the Registry record serve different purposes and are not in conflict.

The strategic opportunity is a partnership model: contractors using Angi, Thumbtack,
or similar platforms gain the ability to attach Registry-verified work records
to the properties they serve, differentiating their professional reputation through
verifiable history rather than anonymous reviews.

---

## Category 5: Home Warranty Providers

### Who They Are

Companies that offer service contracts covering repair or replacement of home
systems and appliances. The major players include American Home Shield, Choice
Home Warranty, First American Home Warranty, and Select Home Warranty.

### What They Solve

Home warranty companies provide financial protection against the cost of system
and appliance failures during the coverage period. They are service contract
businesses, not record businesses.

### Why They Do Not Solve the Market Failure

Home warranty providers hold valuable records — which systems are covered, what
service calls have been made, what replacements have been performed under warranty.
These records exist in proprietary systems organized around the warranty contract,
not the property. When the warranty expires or is not renewed, the records become
inaccessible. When the property is sold, the warranty may or may not transfer,
and the service history almost never does.

### Relationship to Haus Registry

Home warranty providers are **Registry Network participants with strong B2B
partnership potential**. Their service records — claims history, system
replacement records, service visit documentation — are among the most valuable
records that could populate a Property Registry. A partnership model in which
warranty service records are contributed to the Registry (with homeowner consent)
would benefit both parties: the Registry gains verified service records, and the
warranty provider gains a differentiation mechanism and a transfer-friendly record
that supports policy continuation across ownership changes.

---

## Category 6: Insurance Carriers and Insurtechs

### Who They Are

Homeowners insurance carriers (State Farm, Allstate, Liberty Mutual, USAA, and
many others) and the growing Insurtech sector developing AI-driven underwriting
and risk assessment tools.

### What They Solve

Insurance carriers solve the property risk transfer problem: pricing and bearing
the financial risk of property damage in exchange for premium payments. Insurtechs
are building the data and AI infrastructure to price that risk more accurately
at the property level.

### Why They Solve a Related But Different Problem

Insurance carriers have significant data about properties — claims history,
inspection records, risk assessments — but this data is proprietary, carrier-
specific, and inaccessible to the broader market. The insurance industry's
response to its profitability crisis (documented in the Market Analysis) is
explicitly moving toward property-level data — satellite imagery, AI-driven
inspections, drone assessments — to price risk more accurately. This is the
industry discovering, independently, that property-level records have value.

They are not building the persistent institutional record. They are building
better snapshots.

### Relationship to Haus Registry

Insurance carriers and Insurtechs are **the most natural B2B customers for
Registry data** in the medium term. A carrier that can access verified maintenance
history, roof replacement records, HVAC service records, and improvement
documentation for a property can price risk more accurately, reduce claims
disputes, and reward well-maintained properties with lower premiums.

This relationship is explored in depth in the Business Model and Monetization
Strategy documents. The competitive risk is minimal: insurance carriers are not
building property lifecycle registries. They are building underwriting tools.
The Registry is the data they need to make those tools more accurate.

---

## The Real Competitive Risks

Having established that no existing company is building what Haus Registry is
building, it is important to name the actual competitive risks — the forces that
could prevent the category from emerging on our terms or at all.

### Risk 1: A Well-Capitalized Adjacent Player Pivots

The most credible competitive threat is not a current competitor but a future
one: a company in an adjacent category — CoreLogic, Zillow, a major home
management app — that recognizes the opportunity and pivots to build a
property-centric, transferable institutional record layer.

**Mitigants:** Speed of execution and record accumulation. The Registry becomes
more valuable with every record added and every year of continuous documentation.
A late entrant with no accumulated records cannot replicate years of property
history regardless of their distribution advantage. The first company to
assemble a meaningful corpus of verified property lifecycle records creates a
compounding moat.

### Risk 2: Consumer Willingness to Pay Does Not Materialize at Scale

If homeowners do not value the Registry Report or My Registry subscription at
a price point that supports the business, the consumer revenue model fails.

**Mitigants:** The B2B revenue model (Registry data licensed to lenders, insurers,
and appraisers) does not depend on consumer willingness to pay. The transaction-
adjacent model (Registry Reports ordered at closing) shifts the payment to the
transaction event rather than the ongoing subscription. Multiple revenue models
reduce dependence on any single one.

### Risk 3: Data Network Effects Fail to Materialize

The Registry's value depends on record completeness. If contributors —
homeowners, contractors, inspectors, manufacturers — do not populate the Registry
in sufficient numbers to produce meaningfully complete records, the Registry
Confidence Score remains low and the product's value proposition is weakened.

**Mitigants:** Pre-population from public records (permits, deeds, assessor data)
provides a foundation before any contributor adds a record. Registry AI extraction
from uploaded documents reduces the data entry burden. Transaction-adjacent
entry points create natural moments of contribution. The minimum viable Registry
— even a sparse one — is more useful than nothing, and every record added makes
the next record more valuable.

### Risk 4: Regulatory Constraints on Data Use

The use of property records for insurance underwriting, mortgage lending decisions,
and appraisal support is subject to federal and state regulation. Failure to
navigate these constraints correctly could limit the B2B revenue potential or
expose the company to liability.

**Mitigants:** Addressed in depth in the Regulatory Considerations document.
The company's commitment to transparency — every record displays its source and
verification level — is itself a regulatory risk mitigation. We never present
uncertain information as certain, and we never use data in ways that participants
have not authorized.

---

## Competitive Positioning Summary

| Category | What They Do | Primary Limitation | Relationship to Haus Registry |
|---|---|---|---|
| Home Management Apps | Personal organization for current owner | Owner-centric; record does not transfer | Different problem; potential future threat if they pivot |
| Property Data Aggregators | Transaction and valuation analytics | No lifecycle records; institution-centric | Potential partners and acquirers; eventual data customers |
| Transaction Platforms | Facilitate buying and selling | Transaction-oriented; no persistent record | Distribution channels; Registry Report entry point |
| Contractor Marketplaces | Match homeowners with professionals | Transaction-oriented; no property record | Registry Network participants; partnership opportunity |
| Home Warranty Providers | Service contract coverage | Contract-centric; records not transferable | Registry Network participants; B2B record contributors |
| Insurance Carriers/Insurtechs | Price and bear property risk | Proprietary snapshot data; not persistent | Primary B2B data customers for Registry |

---

## The Moat

Haus Registry's sustainable competitive advantage is not a feature, a technology,
or a patent. It is the accumulated, verified, persistent institutional record of
every property in its Registry.

The moat has three compounding components:

**Record accumulation:** Every record added to a Property Registry makes that
Registry more valuable. Every year of documented history increases the value
of every prior record. This accumulation cannot be replicated by a late entrant
without years of time — the history either exists or it doesn't.

**Verification network:** As the Registry Network grows — with more contractors,
inspectors, manufacturers, and municipalities contributing verified records —
the verification depth of each Registry increases. The network becomes more
valuable as it grows, creating classic network effects.

**Switching cost:** Once a Property Registry exists for a home, the accumulated
history creates a switching cost for any alternative. The next owner inherits
that history. Switching to a different registry means abandoning years of
documented property memory — the most valuable thing the Registry contains.

These three components compound over time. The longer Haus Registry operates
and the more records it accumulates, the harder it becomes for any competitor
to replicate its value proposition from scratch.

---

*This document defines the competitive landscape as it exists at founding.*
*It should be updated as new entrants emerge, as adjacent players make*
*strategic moves, and as Haus Registry's own market position becomes clearer.*
*Every competitive claim should be rechecked before use in investor materials*
*or partnership discussions.*
