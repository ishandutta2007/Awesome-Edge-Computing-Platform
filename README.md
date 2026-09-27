# Awesome-Edge-Computing-Platform

## Top Edge Computing Platforms Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Edge Functions, WebAssembly Runtimes, Global Distributed Computing & Serverless Architectures*
**Last updated: September 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Edge Computing**. These tools help developers run code closer to users, reduce latency, improve performance, and build globally distributed serverless applications.

**Examples** include Cloudflare Workers, Fastly Compute, Vercel Edge Functions, Netlify Edge Functions, Deno Deploy, Akamai EdgeWorkers, Fermyon Cloud, Edgio Applications, Fly.io, and Render Edge (the category leaders).

**Open-source emphasis**: The open-source ecosystem for edge computing is **polarized**. Commercial platforms (Cloudflare, Fastly, Vercel) dominate the market, but open-source alternatives have matured at the **WebAssembly runtime** level (WasmEdge, wasmCloud) and **Kubernetes-native edge orchestration** level (KubeEdge). This section focuses on **self-hostable Wasm runtimes**, **edge orchestration frameworks**, and **edge function engines**.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Cloudflare Workers](https://workers.cloudflare.com/)**
  The most widely adopted edge computing platform. JavaScript/TypeScript runtime based on V8 isolates with near-zero cold starts. Supports Durable Objects, Cron Triggers, KV storage, and R2 object storage. Worker scripts run across Cloudflare's 300+ data centers globally. Has migrated from Cloudflare Pages to a unified Workers architecture .

- **[Fastly Compute](https://www.fastly.com/products/edge-compute)**
  WebAssembly-based edge computing platform. Uses the open-source Lucet compiler and Wasmtime runtime for extremely fast cold starts. Supports Rust, JavaScript, Go, and other languages. Acquired Fanout in 2024 to add WebSockets and real-time push capabilities, enabling one-to-many broadcast and HTTP push .

- **[Vercel Edge Functions](https://vercel.com/docs/functions/edge-functions)**
  Edge function platform for modern web frameworks (Next.js). As of March 2025, Edge Runtime execution is limited to **300 seconds**, including streaming responses and `waitUntil()` post-processing tasks. However, Edge Functions are now **deprecated**, replaced by Vercel Functions and Routing Middleware running on Fluid compute infrastructure .

- **[Netlify Edge Functions](https://www.netlify.com/products/edge/)**
  Edge function platform built on the **Deno runtime**. Supports JavaScript/TypeScript to modify network requests, localize content, authenticate users, and redirect visitors. Edge functions are version-controlled, built, and deployed alongside the site, benefiting from Deploy Previews and rollback capabilities. Real-time logs with Log Drains integration for third-party monitoring .

- **[Deno Deploy](https://deno.com/deploy)**
  Global edge hosting platform built on the Deno runtime. Supports one-click deployment of Deno apps to a global edge network with built-in telemetry and CI/CD tooling. Automatically detects configuration from GitHub repositories and deploys, with Logs, Traces, and Metrics observability tools .

- **[Akamai EdgeWorkers](https://www.akamai.com/products/edgeworkers)**
  Event-driven serverless platform embedded directly into the CDN. JavaScript (V8) runtime executing on Akamai's thousands of edge nodes. Focused on **traffic orchestration**: request routing, A/B testing, auth token validation, cache key customization. Execution time **<10 seconds** with low CPU/memory limits, optimized for CDN traffic handling rather than general-purpose compute. Pairs with EdgeKV for edge data storage .

- **[Fermyon Cloud](https://www.fermyon.com/cloud)**
  Multi-tenant, globally distributed serverless function engine based on WebAssembly, running on Akamai Cloud. **Cold starts at 0.52 milliseconds**, supporting Rust, Go, JavaScript, Python, TypeScript, and more. `spin aka deploy` deploys to Akamai's global network with one command. Suitable for AI inference, traffic mirroring, and similar scenarios .

- **[Edgio Applications](https://edg.io/)**
  Edge application platform (formerly Layer0). Provides edge functions, CDN, and performance optimization capabilities.

- **[Fly.io](https://fly.io/)**
  Distributed application platform that runs containerized apps at edge locations close to users. Launched **Sprites** in 2026 (disposable cloud computers) designed specifically for AI agents, with MCP integration and progressive CLI disclosure .

- **[Render Edge](https://render.com/)**
  Fully managed cloud platform offering web services, WebSocket support, and edge computing capabilities. Render does not enforce a maximum WebSocket connection duration, but instance restarts or platform maintenance may interrupt connections, requiring clients to implement exponential backoff reconnection logic .

## Open-Source GitHub Projects

### WebAssembly Runtimes & Engines

- **[WasmEdge](https://github.com/WasmEdge/WasmEdge)**
  Lightweight, high-performance, extensible WebAssembly runtime for cloud-native, edge, and decentralized applications. Supports serverless apps, embedded functions, microservices, smart contracts, and IoT devices. CNCF sandbox project, with Debian providing a `libwasmedge0` package .

- **[wasmCloud](https://github.com/wasmCloud/wasmCloud)**
  Universal application platform that compiles code to WebAssembly components runnable anywhere—from laptop to edge to cloud. Built on the **Wasmtime** runtime, with components communicating through interfaces and a lattice providing a self-forming, self-healing mesh network. **Relationship to Kubernetes**: wasmCloud is to WebAssembly components what Kubernetes is to containers. Can run standalone or integrate with Kubernetes via an Operator .

- **[SpinKube](https://github.com/spinkube/spinkube)**
  Open-source project for deploying and running Wasm workloads on Kubernetes. Combines **Spin Operator**, **runwasi**, and **runtime class manager**. Wasm artifacts are much smaller than container images, start faster, and consume fewer resources at idle. Integrates with Kubernetes primitives: DNS, probes, autoscaling, metrics. CNCF sandbox project .

- **[NovaCompute](https://github.com/anand-exe7/NovaCompute)**
  Multi-tenant Wasm serverless edge engine written in pure Go. **Zero Docker, zero cold starts**. Built on wazero (pure Go Wasm engine, WASI Snapshot Preview 1). Features memory hot-pool manager (sub-millisecond execution), weighted semaphore backpressure (max 10 concurrent), GC eviction (10-minute TTL), PostgreSQL + Redis dual storage, and multi-tenant sliding window rate limiting. Deployable to AWS, bare metal, GCP, or Kubernetes .

### Edge Orchestration & Kubernetes

- **[KubeEdge](https://github.com/kubeedge/kubeedge)**
  CNCF graduated project, Kubernetes-native edge computing framework. Extends containerized application orchestration to edge hosts with cloud-edge synergy. **Edge autonomy**: nodes continue operating independently when disconnected. Memory footprint around **70MB**. Supports x86, ARMv7, ARMv8. Latest version v1.22.0 (November 2025).

- **[Baetyl](https://github.com/baetyl/baetyl)**
  LF Edge project (donated by Baidu) that seamlessly extends cloud computing, data, and services to edge devices. Built-in support for 30+ industrial protocols and MLflow AI inference integration. China's first open-source edge computing platform.

- **[EVE-OS (Project EVE)](https://github.com/lf-edge/eve)**
  LF Edge edge virtualization engine contributed by ZEDEDA. Open, neutral, standardized architecture for orchestrating cloud-native applications at enterprise on-premises edge. Provides hardware-assisted virtualization and container/K8s runtimes with declarative APIs supporting intermittent connectivity and disconnected operations.

### Edge Functions & Serverless

- **[OpenFaaS](https://github.com/openfaas/faas)**
  Open-source serverless framework for running functions on Kubernetes. Supports any language packaged as Docker containers. Deployable to edge nodes.

- **[Knative](https://github.com/knative/serving)**
  Serverless platform on Kubernetes. Provides request-driven autoscaling and event-driven architecture, runnable on edge Kubernetes clusters.

- **[Nuclio](https://github.com/nuclio/nuclio)**
  High-performance serverless framework focused on real-time data processing and AI inference. Supports Kubernetes and edge deployments.

### Additional Strong Open-Source Options

- **WebAssembly Runtimes**: **WasmEdge** (CNCF sandbox, lightweight), **wasmCloud** (universal application platform), **Wasmtime** (Bytecode Alliance, wasmCloud's foundation), **wasmer** (high-performance Wasm runtime).
- **Edge Kubernetes**: **KubeEdge** (CNCF graduated, edge autonomy), **K3s** (lightweight Kubernetes), **MicroK8s** (Canonical).
- **Edge Serverless**: **OpenFaaS**, **Knative**, **Nuclio**, **NovaCompute** (pure Go Wasm engine).
- **Edge Orchestration**: **Baetyl** (LF Edge, industrial protocols), **EVE-OS** (edge virtualization), **SpinKube** (Wasm on Kubernetes).

**Frameworks for building custom systems**: Combine **wasmCloud** or **WasmEdge** as the Wasm runtime core, **KubeEdge** or **SpinKube** for Kubernetes-native edge orchestration, **NovaCompute** for multi-tenant Wasm function execution, and **OpenFaaS** or **Knative** for serverless function management. Add **NATS** for lattice communication and **PostgreSQL + Redis** for persistence.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Edge computing platforms handle potentially sensitive application and user data; ensure compliance with relevant data protection regulations.
- **Open-source reality**: The open-source ecosystem is mature at the **WebAssembly runtime** level (WasmEdge, wasmCloud) and **Kubernetes edge orchestration** level (KubeEdge), but lacks direct open-source alternatives to **fully managed edge function platforms** (Cloudflare Workers, Vercel Edge Functions). Self-hosted solutions require engineering teams to manage distributed infrastructure, global routing, and runtime security.

---

**Made for edge computing engineers, serverless developers, platform architects, and web performance teams.**
Let's make edge computing more open, portable, and performant.
