---
marp: true
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

# <span class="main-title">Storage Efficiency: Parquet vs JSON vs CSV</span>
* **Focus**: Data Format Engineering
* **Goal**: Minimize Storage & Maximize Query Speed
* **Impact**: 90% Cloud Cost Reduction

---

## The Problem: The "Text" Tax
<span class="item-sub">Using CSV or JSON for Big Data is like trying to find a single word in a pile of unindexed books.</span>

<div class="item-group">
  <span class="item-main">I/O Inefficiency</span>
  <span class="item-sub">To read 1 column in a CSV, you must scan the <b>entire row</b>. 90% of I/O is wasted.</span>
</div>

<div class="item-group">
  <span class="item-main">Data Redundancy</span>
  <span class="item-sub">JSON repeats keys (e.g., "id":) for <b>every single record</b>, bloating size by 5x-10x.</span>
</div>

---

## Strategy 1: Columnar Revolution (Parquet)
<span class="item-sub">Switch from Row-based to Column-based storage to unlock massive performance.</span>

<div class="item-group">
  <span class="item-main">Projection Pushdown</span>
  <span class="item-sub">Only load the columns you need. Reduce data scan from 1TB to 10MB instantly.</span>
</div>

<div class="item-group">
  <span class="item-main">Built-in Metadata</span>
  <span class="item-sub">Files store Min/Max stats per block. Query engines skip irrelevant data without reading it.</span>
</div>

---

## Strategy 2: Intelligent Encoding
<span class="item-sub">Parquet doesn't just store data; it optimizes it at the bit level.</span>

<div class="item-group">
  <span class="item-main">Dictionary Encoding</span>
  <span class="item-sub">Replaces long repetitive strings with tiny integers. Massive space savings.</span>
</div>

<div class="item-group">
  <span class="item-main">Delta & RLE</span>
  <span class="item-sub">Compresses sequences (like timestamps or sensor IDs) into a fraction of their size.</span>
</div>

---

## Strategy 3: Write vs Read Optimization
<span class="item-sub">Not all binary formats are equal. Choose based on your pipeline stage.</span>

<div class="item-group">
  <span class="item-main">Avro (Write-Optimized)</span>
  <span class="item-sub">Binary Row-based. Ideal for <b>Streaming Ingestion</b> and high-speed appenders.</span>
</div>

<div class="item-group">
  <span class="item-main">Parquet (Read-Optimized)</span>
  <span class="item-sub">Column-based. Ideal for <b>Data Lakes & Analytics</b> where query speed is King.</span>
</div>

---

## The Cloud Payoff: Cost Governance
<span class="item-sub">On AWS Athena or GCP BigQuery, you pay per TB scanned. Parquet is your wallet's best friend.</span>

<div class="item-group">
  <span class="item-main">90% Cost Reduction</span>
  <span class="item-sub">Parquet's compression and columnar nature slash the <b>Cloud Tax</b> drastically.</span>
</div>

<div class="item-group">
  <span class="item-main">Storage Density</span>
  <span class="item-sub">1GB of raw JSON typically shrinks to <b><150MB</b> in Parquet.</span>
</div>

---

## Comparison Matrix: The DE Choice
<span class="item-sub">Selecting the right tool for the right volume:</span>

<div class="item-group">
  <span class="item-main">CSV/JSON</span>
  <span class="item-sub">Small datasets (<100MB), human readability required.</span>
</div>

<div class="item-group">
  <span class="item-main">Binary / Parquet</span>
  <span class="item-sub">Big Data (>1GB), Analytics, and Production Pipelines.</span>
</div>

---

><span class="item-sub"><i>Data Engineer Insight: Stop Scanning Text</i> <br>
><b>If you are still querying CSVs in 2026, you are leaking budget.</b>
A top-tier DE doesn't just move data; they engineer its physical layout. 
Parquet isn't just a file; it's an indexed, compressed, and self-describing asset.</span>

---

## 💡 Efficiency Opportunity

<span class="item-sub">
Is your Data Lake a dumping ground for text files or an optimized engine?
<b>Efficiency starts at the schema level</b>.

Don't let uncompressed JSON choke your bandwidth. Implement <b>Parquet</b> to ensure your analytics are fast and cheap.
</span>

<span class="item-sub">
Are your pipelines <b>schema-aware</b> enough to handle automated transformations?

Is your storage strategy truly optimized for the <i>Cloud</i>? Does it guarantee <b>high-speed retrieval</b>?
</span>
