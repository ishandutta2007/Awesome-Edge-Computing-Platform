# Awesome-Edge-Computing-Platform

# 顶级边缘计算平台生态系统



**精选 SaaS 产品与开源 GitHub 项目列表**

*聚焦边缘函数、WebAssembly 运行时、全球分布式计算与无服务器架构*

**最后更新：2026 年 9 月**



本仓库追踪**边缘计算**领域的知名 **SaaS 平台**与**开源项目**。这些工具帮助开发者在靠近用户的位置运行代码，降低延迟、提升性能，并构建全球分布式的无服务器应用。



**示例**包括 Cloudflare Workers、Fastly Compute、Vercel Edge Functions、Netlify Edge Functions、Deno Deploy、Akamai EdgeWorkers、Fermyon Cloud、Edgio Applications、Fly.io 和 Render Edge（该领域的领先者）。



**开源重点**：边缘计算领域的开源生态呈现**两极分化**。商业平台（Cloudflare、Fastly、Vercel）主导市场，但开源替代方案在 **WebAssembly 运行时**（WasmEdge、wasmCloud）和 **Kubernetes 原生边缘编排**（KubeEdge）层面已经成熟。本列表重点收录**可自托管的 Wasm 运行时**、**边缘编排框架**和**边缘函数引擎**。



欢迎贡献！提交 PR 以添加/更新条目。保持描述事实性，并链接到官方网站。



## 目录



- [SaaS/托管平台](#saas托管平台)

- [开源 GitHub 项目](#开源github项目)

- [如何贡献](#如何贡献)

- [免责声明](#免责声明)



## SaaS/托管平台



- **[Cloudflare Workers](https://workers.cloudflare.com/)**

  最广泛采用的边缘计算平台。基于 V8 隔离区（isolates）的 JavaScript/TypeScript 运行时，冷启动接近零。支持 Durable Objects、Cron Triggers、KV 存储和 R2 对象存储。Worker 脚本在 Cloudflare 全球 300+ 数据中心运行。已从 Cloudflare Pages 迁移至 Workers 统一架构 。



- **[Fastly Compute](https://www.fastly.com/products/edge-compute)**

  基于 WebAssembly 的边缘计算平台。使用开源 Lucet 编译器和 Wasmtime 运行时，冷启动速度极快。支持 Rust、JavaScript、Go 等语言。2024 年收购 Fanout 后增加了 WebSockets 和实时推送能力，支持一对多广播和 HTTP 推送 。



- **[Vercel Edge Functions](https://vercel.com/docs/functions/edge-functions)**

  面向现代 Web 框架（Next.js）的边缘函数平台。2025 年 3 月起，Edge Runtime 执行时长限制为 **300 秒**，包括流式响应和 `waitUntil()` 后处理任务。但 Edge Functions 已**弃用**，被 Vercel Functions 和 Routing Middleware 取代，统一运行在 Fluid compute 基础设施上 。



- **[Netlify Edge Functions](https://www.netlify.com/products/edge/)**

  基于 **Deno 运行时**的边缘函数平台。支持 JavaScript/TypeScript，可修改网络请求、本地化内容、认证用户、重定向访客。边缘函数与站点一起版本控制、构建和部署，享受 Deploy Previews 和回滚能力。日志实时显示，支持 Log Drains 集成第三方监控 。



- **[Deno Deploy](https://deno.com/deploy)**

  基于 Deno 运行时的全球边缘托管平台。支持 Deno 应用一键部署到全球边缘网络，内置遥测和 CI/CD 工具。从 GitHub 仓库自动检测配置并部署，提供 Logs、Traces 和 Metrics 可观测性工具 。



- **[Akamai EdgeWorkers](https://www.akamai.com/products/edgeworkers)**

  直接嵌入 CDN 的事件驱动无服务器平台。JavaScript（V8）运行时，在 Akamai 数千个边缘节点执行。专注于**流量编排**：请求路由、A/B 测试、认证令牌验证、缓存键定制。执行时间 **<10 秒**，CPU/内存限制较低，优化用于 CDN 流量处理而非通用计算。搭配 EdgeKV 用于边缘数据存储 。



- **[Fermyon Cloud](https://www.fermyon.com/cloud)**

  基于 WebAssembly 的多租户、全球分布式无服务器函数引擎，运行在 Akamai Cloud 上。**冷启动 0.52 毫秒**，支持 Rust、Go、JavaScript、Python、TypeScript 等多种语言。`spin aka deploy` 一行命令部署到 Akamai 全球网络。适合 AI 推理、流量镜像等场景 。



- **[Edgio Applications](https://edg.io/)**

  边缘应用平台（原 Layer0）。提供边缘函数、CDN 和性能优化能力。



- **[Fly.io](https://fly.io/)**

  分布式应用平台，在靠近用户的边缘位置运行容器化应用。2026 年推出 **Sprites**（一次性云计算机），专为 AI 代理设计，支持 MCP 集成和 CLI 渐进式披露 。



- **[Render Edge](https://render.com/)**

  全托管云平台，提供 Web 服务、WebSocket 支持和边缘计算能力。Render 不强制 WebSocket 连接最大时长，但实例重启或平台维护可能中断连接，需要客户端实现指数退避重连逻辑 。



## 开源 GitHub 项目



### WebAssembly 运行时与引擎



- **[WasmEdge](https://github.com/WasmEdge/WasmEdge)**

  轻量级、高性能、可扩展的 WebAssembly 运行时，用于云原生、边缘和去中心化应用。支持无服务器应用、嵌入式函数、微服务、智能合约和 IoT 设备。CNCF 沙箱项目，Debian 提供 `libwasmedge0` 包 。



- **[wasmCloud](https://github.com/wasmCloud/wasmCloud)**

  通用应用平台，将代码编译为 WebAssembly 组件后可在任何环境运行——从笔记本到边缘到云。基于 **Wasmtime** 运行时，组件通过接口通信，lattice 提供自形成、自修复的网格网络。**与 Kubernetes 的关系**：wasmCloud 之于 WebAssembly 组件，如同 Kubernetes 之于容器。可独立运行或通过 Kubernetes Operator 集成 。



- **[SpinKube](https://github.com/spinkube/spinkube)**

  在 Kubernetes 上部署和运行 Wasm 工作负载的开源项目。结合 **Spin Operator**、**runwasi** 和 **runtime class manager**。Wasm 工件比容器镜像小得多、启动更快、空闲时资源消耗更低。与 Kubernetes 原语集成：DNS、探针、自动扩缩、指标。CNCF 沙箱项目 。



- **[NovaCompute](https://github.com/anand-exe7/NovaCompute)**

  纯 Go 编写的多租户 Wasm 无服务器边缘引擎。**零 Docker、零冷启动**。基于 wazero（纯 Go Wasm 引擎，WASI Snapshot Preview 1）。功能包括内存热池管理器（亚毫秒执行）、加权信号量背压（最大 10 并发）、GC 驱逐（10 分钟 TTL）、PostgreSQL + Redis 双存储、多租户滑动窗口限流。可部署到 AWS、裸金属、GCP 或 Kubernetes 。



### 边缘编排与 Kubernetes



- **[KubeEdge](https://github.com/kubeedge/kubeedge)**

  CNCF 毕业项目，Kubernetes 原生边缘计算框架。将容器化应用编排扩展到边缘主机，提供云边协同。**边缘自治**：节点断连时仍能独立运行。内存占用约 **70MB**。支持 x86、ARMv7、ARMv8。最新版本 v1.22.0（2025 年 11 月）。



- **[Baetyl](https://github.com/baetyl/baetyl)**

  LF Edge 项目（百度捐赠），将云计算、数据和服务无缝扩展到边缘设备。内置 30+ 工业协议支持和 MLflow AI 推理集成。中国首个开源边缘计算平台。



- **[EVE-OS (Project EVE)](https://github.com/lf-edge/eve)**

  LF Edge 边缘虚拟化引擎，由 ZEDEDA 贡献。开放、中立的标准化架构，用于在企业本地边缘编排云原生应用。提供硬件辅助虚拟化和容器/K8s 运行时，声明式 API 支持间歇连接和断连操作。



### 边缘函数与 Serverless



- **[OpenFaaS](https://github.com/openfaas/faas)**

  开源无服务器框架，可在 Kubernetes 上运行函数。支持任何语言，通过 Docker 容器打包。可部署到边缘节点。



- **[Knative](https://github.com/knative/serving)**

  Kubernetes 上的无服务器平台。提供请求驱动的自动扩缩、事件驱动架构，可运行在边缘 Kubernetes 集群。



- **[Nuclio](https://github.com/nuclio/nuclio)**

  高性能无服务器框架，专注于实时数据处理和 AI 推理。支持 Kubernetes 和边缘部署。



### 其他强开源选项



- **WebAssembly 运行时**：**WasmEdge**（CNCF 沙箱，轻量级）、**wasmCloud**（通用应用平台）、**Wasmtime**（Bytecode Alliance，wasmCloud 底层）、**wasmer**（高性能 Wasm 运行时）。

- **边缘 Kubernetes**：**KubeEdge**（CNCF 毕业，边缘自治）、**K3s**（轻量级 Kubernetes）、**MicroK8s**（Canonical）。

- **边缘 Serverless**：**OpenFaaS**、**Knative**、**Nuclio**、**NovaCompute**（纯 Go Wasm 引擎）。

- **边缘编排**：**Baetyl**（LF Edge，工业协议）、**EVE-OS**（边缘虚拟化）、**SpinKube**（Kubernetes 上的 Wasm）。



**构建自定义系统的框架**：结合 **wasmCloud** 或 **WasmEdge** 作为 Wasm 运行时核心，**KubeEdge** 或 **SpinKube** 用于 Kubernetes 原生边缘编排，**NovaCompute** 用于多租户 Wasm 函数执行，**OpenFaaS** 或 **Knative** 用于无服务器函数管理。添加 **NATS** 用于 lattice 通信，**PostgreSQL + Redis** 用于持久化。



## 如何贡献



1. Fork 仓库。

2. 在 `README.md` 中添加/编辑条目（遵循现有格式）。

3. 包含：名称、链接、1-2 句描述，以及是 SaaS 还是开源。

4. 提交 PR 并附简短说明。



如果你觉得这个仓库有用，请点星！



## 免责声明



- 这是一个**社区精选**列表——并非详尽无遗，也不构成认可。

- 边缘计算平台处理可能敏感的应用和用户数据；确保遵守相关数据保护法规。

- **开源现实**：边缘计算的开源生态在 **WebAssembly 运行时**（WasmEdge、wasmCloud）和 **Kubernetes 边缘编排**（KubeEdge）层面已经成熟，但在**完全托管的边缘函数平台**（如 Cloudflare Workers、Vercel Edge Functions）层面仍缺乏直接的开源替代。自托管方案需要工程团队管理分布式基础设施、全球路由和运行时安全。



---



**为边缘计算工程师、无服务器开发者、平台架构师和 Web 性能优化团队打造。**

让边缘计算更开放、可移植、高性能。
