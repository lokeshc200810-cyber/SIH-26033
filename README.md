# Smart India Hackathon Workshop

# Date:26/10/2026

## Reference Number:26018290

## Name:lokesh c

## Problem Title

SIH 26033: Multiple intermediaries reduce farmers earnings and increase consumer prices.

## Problem Creater's Organization

Ministry of Consumer Affairs, Food & Public Distribution

## Theme

Agriculture, FoodTech & Rural Development

## Problem Description

Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution

Detailed Explanation of the Proposed Solution
PayirSetu (AgriPact & Cold-Buffer Grid) is an AI-driven Pre-Harvest Forward-Contract Exchange, Solar Micro-Cold Storage, and Backhaul Freight Aggregation Platform built for smallholder farmers and Farmer Producer Organizations (FPOs) dealing in highly perishable horticulture crops.
Rather than forcing farmers to harvest blindly and dump produce at congested mandis through layers of commission agents, PayirSetu combines Satellite Crop-Readiness Mapping, Automated Buyer Reverse-Auctions, and Panchayat-Level Solar Cooling Pods. Institutional buyers (cloud kitchens, retail chains, food processors, export houses, and urban housing societies) bid directly on upcoming harvests via digital forward pacts. If market prices dip on harvest day, farmers can store produce in local phase-change solar cooling pods for 5 to 7 days to prevent distress selling while utilizing empty return-trip ("backhaul") commercial trucks for low-cost direct city delivery.
How It Addresses the Problem

- Replaces Mandi Distress Sales with Forward Pacts: Locks in buyer commitments and guaranteed floor prices 7 to 14 days before harvest using digital smart contracts, eliminating commission agent monopolies.
- Prevents Post-Harvest Spoilage & Price Crashes: Provides pay-per-crate access to decentralized, off-grid solar micro-cold storage at village clusters, extending crop shelf-life by up to 7 days when spot market rates crash.
- Slashes Rural Transport Costs via Backhaul Matching: Aggregates empty commercial vehicles returning from rural deliveries to cities (deadhead freight), cutting farmer logistics expenses by 35–45% compared to dedicated truck hires.
- Automated Quality-Linked UPI Escrow: Releases 100% of the trade value directly to the farmer's bank account via UPI AutoPay upon AI visual quality verification and dispatch scan.
  Innovation and Uniqueness of the Solution
- Deadhead Backhaul Freight Engine: Instead of maintaining an expensive dedicated fleet, the platform uses spatial indexing to match village harvest loads with empty trucks and rural cargo buses already returning toward urban centers.
- Glut-Prevention Satellite Advisory: Uses satellite vegetation indices and regional listing density to detect localized oversupply early, automatically routing surplus produce to distant deficit markets or food processing plants.
- Zero-App WhatsApp & Voice Bot Trade Desk: Farmers can list crops, receive AI-checked quality certificates, and accept buyer forward bids purely through WhatsApp voice notes or toll-free missed-call IVR in their native language.

## Technical Approach

Technologies to Be Used

- Web & Mobile Frontend: Next.js (TypeScript) web portal for institutional buyers, processors, and FPO operators; React Native lightweight mobile app for rural logistics partners and storage operators.
- Conversational & Voice Interface: WhatsApp Business Cloud API integrated with OpenAI Whisper / AI4Bharat IndicConformer for vernacular voice-note trade booking and Twilio/Exotel missed-call IVR.
- Backend & Interoperability Layer: Go (Golang) and Python (FastAPI) microservices supporting e-NAM / ONDC Beckn Protocol gateways and event-driven Apache Kafka pipelines for real-time reverse bidding.
- AI, Geospatial & IoT Modules:
  - Harvest & Glut Prediction: Google Earth Engine (Sentinel-2 NDVI imagery) combined with Prophet/XGBoost time-series models to predict regional harvest volumes and price dips.
  - Edge Visual Assaying: YOLOv8-Nano running on edge devices to detect rot, bruising, and size distribution from a 5-second video clip.
  - IoT Cold-Pod Telemetry: ESP32 microcontrollers with DHT22 temperature/ethylene sensors communicating via MQTT to monitor solar phase-change cooling pods.
- Database & Spatial Indexing: PostgreSQL with Uber H3 Hexagonal Spatial Index for real-time backhaul truck matching; Redis for live auction state management.
  ##Technical Architecture & Workflow Diagram
  ```mermaid
  graph TD
  A[Smallholder Farmer: WhatsApp Voice / Missed-Call IVR] -->|Registers Upcoming Harvest| B(Satellite NDVI & YOLOv8-Nano Quality Assay)
  C[Institutional Buyers, Processors & RWAs] -->|Places Forward Bids & Funds UPI Escrow| D{PayirSetu Reverse-Auction & Glut Engine}
  E[e-NAM & Agmarknet Price Parity AI] --> D
  B --> D
  D -->|Price Favorable: Direct Dispatch| F[Uber H3 Backhaul Empty-Truck Matcher]
  D -->|Price Crash Detected: Hold Produce| G[IoT Solar Micro-Cold Pod + 75% Instant Credit Advance]
  G -->|Dispatches When Price Recovers| F
  F -->|Direct Farm-to-Buyer Transit| C
  C -->|Digital Assay & Delivery Handshake| H[RazorpayX Automated Split UPI Settlement]
  H -->|Direct Bank Payout| A
  H -->|Backhaul Freight & Cold-Storage Fee| F
  ```

## Methodology and Process for Implementation

- Pre-Harvest Listing & Satellite Verification: Farmers send a voice note or photo via WhatsApp 10 days before harvest; the backend cross-checks farm location with Sentinel-2 crop maturity data and generates a verified digital lot.
- Reverse-Auction Forward Matching: Institutional buyers bid on pooled village lots above an AI-calculated floor price (indexed to live e-NAM/Agmarknet rates), locking funds into a digital UPI escrow account.
- Edge Video Assay & Smart Buffering: At harvest, a 5-second smartphone video grades the produce via YOLOv8-Nano. If regional prices are depressed, the lot is buffered in the village IoT Solar Cooling Pod while the farmer receives an instant 75% pledge advance.
- Backhaul Freight Dispatch: Using Uber H3 hexagonal geospatial matching, the system intercepts commercial trucks returning empty along nearby state highways to pick up the consolidated village load at discounted backhaul rates.
- Instant Split Settlement: Upon buyer delivery confirmation via OTP/QR handshake, the escrow smart contract instantly settles the farmer's remaining balance, the truck driver's backhaul fee, and the FPO cold-pod usage charge.

## Feasibility and Viability

Analysis of the Feasibility of the Idea

- Technical Feasibility: Leverages proven cloud and edge technologies (YOLOv8-Nano, Uber H3, WhatsApp Cloud API, Sentinel-2 public satellite APIs) that require zero specialized hardware from the farmer.
- Operational Viability: Avoids heavy capital expenditure by utilizing existing empty return-trip commercial vehicles for logistics and deploying modular, solar-powered cooling units managed by local FPOs or Panchayat Self-Help Groups (SHGs).
- Financial Viability: Operates on a self-sustaining 3.5% transaction fee plus a nominal ₹0.50/kg/day micro-cold storage fee, delivering net savings of 25–30% over traditional mandi-broker supply chains.
  Potential Challenges and Risks
- Buyer Default on Forward Contracts: Buyers might attempt to cancel pre-harvest orders if open-market mandi prices drop sharply before delivery.
- Backhaul Truck Timing Mismatches: Empty return trucks may not always align perfectly with rural harvest pickup windows.
- Cold-Pod Maintenance in Remote Villages: Power fluctuations or mechanical issues in rural areas could risk stored produce.
  Strategies for Overcoming These Challenges
- Non-Refundable Margin Deposit: Buyers must lock a 20% earnest money deposit into UPI escrow when signing a forward pact, which automatically forfeits to the farmer in case of unilateral cancellation.
- Solar Cold-Pod Buffer Window: Because village solar pods keep produce fresh for up to 7 days, pickups do not require minute-by-minute truck synchronization—loads wait safely in climate-controlled buffers until a backhaul vehicle arrives within a 12-hour window.
- Battery-Free Phase-Change Thermal Storage: The cooling pods use solar-charged Phase-Change Material (PCM) thermal plates rather than complex chemical batteries, maintaining cooling for 36 hours without sunlight and sending automated MQTT health alerts to local technicians.

## Impact and Benefits

Potential Impact on the Target Audience

- Farmers & FPOs: Grants holding power against market crashes, eliminates distress selling, and provides direct access to high-margin institutional buyers across state borders.
- Institutional Buyers & Consumers: Secures predictable forward supply, consistent AI-verified quality grades, and 20% lower procurement costs with full farm-origin traceability.
  Benefits of the Solution
- Economic Benefits: Boosts net farmer realization by 40–55% through forward price locking and zero commission fees, while generating additional income for rural truckers on otherwise empty return trips.
- Social Benefits: Empowers smallholders with financial liquidity via instant storage-backed micro-advances and builds localized agri-entrepreneurship around village cooling hubs.
- Environmental Benefits: Cuts carbon emissions by utilizing existing empty truck capacity (reducing redundant freight trips) and uses clean solar thermal energy to reduce post-harvest crop wastage to less than 4%.

## Research and References

- ICAR-CIPHET (Central Institute of Post-Harvest Engineering & Technology): National study on quantitative post-harvest losses of horticulture crops in India ([https://ciphet.icar.gov.in/](https://ciphet.icar.gov.in/)).
- National Agriculture Market (e-NAM): Guidelines on interstate direct agri-trade and electronic assaying standards ([https://enam.gov.in/](https://enam.gov.in/)).
- European Space Agency — Sentinel-2 Mission: Open satellite multispectral imagery for crop health and harvest readiness monitoring ([https://sentiwiki.copernicus.eu/web/sentinel-2](https://sentiwiki.copernicus.eu/web/sentinel-2)).
- Uber H3 Spatial Index Documentation: Hexagonal hierarchical geospatial indexing for real-time logistics and freight matching ([https://h3geo.org/](https://h3geo.org/)).
- NABARD (National Bank for Agriculture and Rural Development): Framework for FPO-led decentralized rural storage and micro-credit linkage ([https://www.nabard.org/](https://www.nabard.org/)).
