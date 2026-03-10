---
marp: false
theme: uncover
class: invert
paginate: true
footer: '@AF'
backgroundColor: #0d1117
style: |
  .main-title { font-size: 0.8em; color: #88b6ff; font-weight: 800; }
  .extra-title { font-size: 1.0em; color: #f53e48; font-weight: 800; }
  .extra-title::before { content: "☕"; margin-right: 0.25em; color: #800000; vertical-align: middle; }
  section { font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; padding: 50px; text-align: left; display: flex; flex-direction: column; justify-content: center; align-items: flex-start; }
  footer { position: absolute !important; top: 15px !important; right: 30px !important; left: auto !important; font-size: 18px !important; font-weight: 900 !important; color: #58a6ff !important; z-index: 1000; }
  h1 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  h2 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  .line { width: 100%; height: 2px; background: #58a6ff; margin: 8px 0 25px 0; }
  .item-group { margin-bottom: 25px; width: 100%; border-left: 4px solid #58a6ff; padding-left: 20px; }
  .item-main { font-size: 0.85em; font-weight: bold; color: #ffffff; display: block; text-transform: uppercase; }
  .item-sub { font-size: 0.65em; color: #a5adba; display: block; margin-top: 5px; }
  .big-text { font-size: 1.5em; color: #58a6ff; vertical-align: middle; }
  .small-text { font-size: 0.6em; color: #a5adba; vertical-align: middle; }

---

![bg opacity:0.4 brightness:0.35](./../scenario_background.png)

# <span class="main-title">Edge Data Governance: Implementing QoS</span>
* **Focus**: Network & Flow Control
* **Goal**: Guaranteed Delivery for Critical Data
* **Impact**: SLA Compliance & Predictable Pipelines

---

## The Problem: Network Anarchy
<span class="item-sub">Without Quality of Service (QoS), every packet is treated equally. A 50MB log file can choke a 1KB emergency alert.</span>

<div class="item-group">
  <span class="item-main">Packet Loss Impact</span>
  <span class="item-sub">In congested FIFO queues, <b>1% packet loss</b> can reduce TCP throughput by <b>>50%</b>.</span>
</div>

<div class="item-group">
  <span class="item-main">Critical Delays</span>
  <span class="item-sub">Non-prioritized alerts can suffer <b>latency spikes from 50ms to 5s+</b>.</span>
</div>

---

## Strategy 1: DSCP Marking (The Priority Pass)
<span class="item-sub">Tag your "Hot Data" at the source to bypass noise in the gateway.</span>

<div class="item-group">
  <span class="item-main">EF (Expedited Forwarding)</span>
  <span class="item-sub">Reserved for Critical Alerts. Aim for <b>Latency < 20ms</b>.</span>
</div>

<div class="item-group">
  <span class="item-main">AF41 (Assured Forwarding)</span>
  <span class="item-sub">Real-time Telemetry (Kafka/Flink). Guaranteed bandwidth allocation.</span>
</div>

<div class="item-group">
  <span class="item-main">BE (Best Effort)</span>
  <span class="item-sub">Bulk logs and historical uploads. Throttled during peak congestion.</span>
</div>

---

## Strategy 2: Jitter Stabilization
<span class="item-sub">Streaming engines like Kafka or Flink require a steady heartbeat to function correctly.</span>

<div class="item-group">
  <span class="item-main">Avoid Buffer Starvation</span>
  <span class="item-sub">QoS keeps <b>Jitter < 5ms</b>, preventing "stuttering" in time-windowed transforms.</span>
</div>

<div class="item-group">
  <span class="item-main">Consistent Windowing</span>
  <span class="item-sub">Ensures data arrives within the expected <b>watermark</b>, reducing late-arrival drops.</span>
</div>

---

## Strategy 3: Traffic Shaping & Backpressure
<span class="item-sub">Don't let the network drop data randomly. Shape it at the source.</span>

<div class="item-group">
  <span class="item-main">Token Bucket Throttling</span>
  <span class="item-sub">Cap non-essential streams (e.g., limit logs to <b>10% of total bandwidth</b>).</span>
</div>

<div class="item-group">
  <span class="item-main">Intelligent Backpressure</span>
  <span class="item-sub">Signal the Edge app to slow down ingestion <b>before</b> the buffer overflows.</span>
</div>

---

## The DE Payoff: Measurable SLAs
<span class="item-sub">QoS transforms a "best effort" network into a professional data pipeline.</span>

<div class="item-group">
  <span class="item-main">Guaranteed Delivery</span>
  <span class="item-sub">Critical data reaches the Cloud with <b>99.9% reliability</b> even during congestion.</span>
</div>

<div class="item-group">
  <span class="item-main">Predictable Freshness</span>
  <span class="item-sub">Data models stay fed with the <b>freshest samples</b>, not delayed batch chunks.</span>
</div>

---

## The Full Stack: Efficiency + Integrity + Governance
<span class="item-sub">Combining the three pillars of Edge Data Engineering:</span>

<div class="item-group">
  <span class="item-main">Efficiency</span>
  <span class="item-sub">Jumbo Frames: <b>-20% CPU</b>, higher throughput.</span>
</div>

<div class="item-group">
  <span class="item-main">Integrity</span>
  <span class="item-sub">Payload Opt: <b>-80% Size</b> via Protobuf & Deduplication.</span>
</div>

<div class="item-group">
  <span class="item-main">Governance</span>
  <span class="item-sub">QoS: <b>Fixed Latency</b> for critical insights.</span>
</div>

---

><span class="item-sub"><i>Data Engineer Insight: Own the Infrastructure</i> <br>
><b>Is your network a black box or a governed asset?</b>
A top-tier Data Engineer protects data timeliness <b>before</b> it hits the Cloud.
If you don't prioritize your packets, the hardware will choose for you—and it will choose wrong.</span>

---

## 💡 QoS & Governance Opportunity

<span class="item-sub">
Are you managing your data flows or just suffering through congestion?
<b>Governance starts at the bit level</b>.

Do not let the router decide what to discard. Implement <b>QoS</b> to ensure your most valuable data always arrives first.
</span>

<span class="item-sub">
Are your edge payloads <b>lean and unique</b> enough to make downstream optimizations effective?

Is your payload truly optimized for the <i>Cloud</i>? Does it guarantee <b>data integrity and timeliness</b>?
</span>
