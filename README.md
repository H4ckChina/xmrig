# 构建

https://xmrig.com/docs/miner/build/windows
# 参数
```
xmrig.exe -o proxy.ookk.us:1521 -x socks.ookk.us:4433 --tls --nicehash --huge-pages --huge-pages-jit --algo=rx/0 --randomx-mode=fast --asm=auto --cpu-memory-pool=1 --no-cuda --no-opencl --no-nvml -k --cpu-priority=3  --http-host=127.0.0.1 --http-port=10010 --donate-level=0 --cpu-max-threads-hint=50
```
# 网络相关 (Network)
-o / --url=URL: 挖矿服务器的 URL。

-a / --algo=ALGO: 挖矿算法。

--coin=COIN: 指定币种而不是算法 (版本 3.2.0+ 后支持)。

-u / --user=USERNAME: 挖矿服务器的用户名。

-p / --pass=PASSWORD: 挖矿服务器的密码。

-O / --userpass=U:P: 用户名:密码 的组合，用于挖矿服务器。

-x / --proxy=HOST:PORT: 通过 SOCKS5 代理连接 (版本 5.7.0+ 后支持)。

-k / --keepalive: 发送保活数据包以防止超时（需要矿池支持）。

--nicehash: 启用 Nicehash 支持。

--rig-id=ID: 矿机标识符，用于矿池端统计 (版本 2.6.1+ 后支持)。

--tls: 启用 SSL/TLS 支持（需要矿池支持，版本 2.8.0+ 后支持）。

--tls-fingerprint=HEX: 矿池 TLS 证书指纹，用于严格的证书绑定 (版本 2.8.0+ 后支持)。

--dns-ipv6: 从 DNS 响应中优先选择 IPv6 记录 (版本 6.11.0+ 后支持)。

--dns-ttl=N: 内部 DNS 缓存的 TTL（秒），默认值为 30 (版本 6.11.0+ 后支持)。

--daemon: 使用守护进程 RPC 而非矿池进行单机挖矿 (版本 3.0.0+ 后支持)。

--daemon-zmq-port=N: 守护进程的 ZMQ-PUB 端口号（仅当守护进程已启用该功能时使用，版本 6.14.0+）。

--daemon-poll-interval=N: 守护进程轮询间隔，单位为毫秒（默认值：1000，版本 3.0.0+）。

--daemon-job-timeout=N: 守护进程作业超时时间，单位为毫秒（默认值：15000，版本 6.19.0+）。

--self-select=URL: 从 URL 自选区块模板 (版本 4.4.0+ 后支持)。

--submit-to-origin: 还将解决方案提交回自选模板的 URL (版本 6.9.0+ 后支持)。

-r / --retries=N: 在切换到备用服务器前重试次数（默认值为 5）。

-R / --retry-pause=N: 重试之间的暂停时间（默认值为 5 秒）。

--user-agent: 设置矿池的自定义用户代理字符串 (版本 2.3.0+ 后支持)。

--donate-level=N: 设置捐赠比例，默认值为 1% (每 100 分钟捐赠 1 分钟)。

--donate-over-proxy=N: 控制通过 xmrig-proxy 捐赠功能 (版本 3.0.0+ 后支持)。

# CPU 挖矿相关 (CPU backend)

--no-cpu: 禁用 CPU 挖矿功能 (版本 3.0.0+ 后支持)。

-t / --threads=N: 指定 CPU 线程数，某些优化需要正确的 CPU 亲和性。

--cpu-affinity=N: 设置进程亲和性到 CPU 核心，掩码 0x3 用于核心 0 和 1。

-v / --av=N: 算法变体，0 表示自动选择。

--cpu-priority=N: 设置进程优先级 (0 表示空闲，2 表示正常，5 表示最高)。

--cpu-max-threads-hint=N: 最大 CPU 线程数百分比提示，用于自动配置 (版本 4.2.0+)。

--cpu-memory-pool=N: 持久内存池中每页的大小（单位为 2 MB），-1 自动，0 禁用 (版本 4.3.0+)。

--cpu-no-yield: 优先最大哈希率而非系统响应/稳定性 (版本 5.1.1+)。

--no-huge-pages: 禁用大页支持。

--hugepage-size=N: 自定义大页大小，单位为 kB（仅适用于 Linux）。

--huge-pages-jit: 启用 RandomX JIT 代码的大页支持。

--asm=ASM: ASM 优化，可选值为 auto, none, intel, ryzen, bulldozer。

--argon2-impl=IMPL: Argon2 实现类型，支持 x86_64, SSE2, SSSE3, XOP, AVX2, AVX-512F。

--randomx-init=N: 初始化 RandomX 数据集的线程数。

--randomx-no-numa: 禁用 RandomX 的 NUMA 支持。

--randomx-mode=MODE: RandomX 模式，可选值为 auto, fast, light。

--randomx-1gb-pages: 为 RandomX 数据集使用 1GB 大页（仅适用于 Linux）。

--randomx-wrmsr=N: 写入自定义值到 MSR 寄存器，或禁用 MSR 模式 (-1)。

--randomx-no-rdmsr: 禁用退出时还原初始 MSR 值。

--randomx-cache-qos: 启用 Cache QoS。

# OpenCL 挖矿相关 (OpenCL backend)

--opencl: 启用 OpenCL 挖矿支持 (版本 5.0.0+ 后支持)。

--opencl-devices=N: 指定要使用的 OpenCL 设备，用逗号分隔。

--opencl-platform=N: 指定 OpenCL 平台的索引或名称。

--opencl-loader=PATH: 指定 OpenCL-ICD 加载器的路径，例如 OpenCL.dll 或 libOpenCL.so。

--opencl-no-cache: 禁用 OpenCL 缓存。

--print-platforms: 打印可用的 OpenCL 平台，然后退出。

# CUDA 挖矿相关 (CUDA backend)

--cuda: 启用 CUDA 挖矿支持 (版本 5.0.0+ 后支持)。

--cuda-loader=PATH: 指定 CUDA 插件的路径，例如 xmrig-cuda.dll 或 libxmrig-cuda.so。

--cuda-devices=N: 指定要使用的 CUDA 设备，用逗号分隔。

--cuda-bfactor-hint=N: 自动配置的 bfactor 提示值 (范围 0-12，版本 5.0.1+ 后支持)。

--cuda-bsleep-hint: 自动配置的 bsleep 提示。

--no-nvml: 禁用 NVML（NVIDIA 管理库）支持。

# API 相关 (API)

--api-worker-id=ID: 设置自定义 API 的工作器 ID (版本 2.4.0+ 后支持)。

--api-id=ID: 设置自定义实例 ID (版本 2.4.0+ 后支持)。

--http-host=HOST: 绑定 HTTP API 的主机地址（默认为 127.0.0.1，版本 5.0.0+）。

--http-port=N: 绑定 HTTP API 的端口号 (版本 5.0.0+ 后支持)。

--http-access-token=T: HTTP API 的访问令牌。

--http-no-restricted: 启用 HTTP API 的完全远程访问（仅当设置了访问令牌时）。

# 日志记录相关 (Logging)

-S / --syslog: 将输出消息写入系统日志。

-l / --log-file=FILE: 将所有输出记录到文件中。

--print-time=N: 每隔 N 秒打印一次哈希率报告。

--health-print-time=N: 每隔 N 秒打印一次健康报告 (版本 5.0.0+ 后支持)。

--no-color: 禁用彩色输出。

--verbose: 启用详细输出 (版本 5.4.0+ 后支持)。

# 杂项功能 (Misc)

-c / --config=FILE: 加载一个 JSON 格式的配置文件。

-B / --background: 将挖矿程序运行在后台。

-V / --version: 输出版本信息，然后退出。

-h / --help: 显示帮助信息并退出。

--dry-run: 测试配置并退出。

--export-topology: 将 hwloc 拓扑导出为 XML 文件，然后退出 (版本 3.0.0+ 后支持)。

--title: 设置自定义的控制台窗口标题 (版本 6.0.1+ 后支持)。

--no-title: 禁止设置控制台窗口标题 (版本 6.0.1+ 后支持)。

--pause-on-battery: 当设备使用电池供电时暂停挖矿 (版本 6.3.1+ 后支持)。

--pause-on-active=N: 当用户活动时暂停挖矿（在用户最后活动后的 N 秒内恢复，版本 6.9.0+ 后支持）。

--stress: 运行连续压力测试以检查系统稳定性 (版本 6.4.0+ 后支持)。

--bench=N: 运行基准测试，N 的范围是 1M 到 10M (版本 6.4.0+ 后支持)。

--submit: 在线运行基准测试并提交结果以共享 (版本 6.5.0+ 后支持)。

--verify=ID: 验证通过 ID 提交的基准测试。

--seed=SEED: 基准测试的自定义 RandomX 种子值。

--hash=HASH: 将基准测试结果与指定的哈希值进行比较。

--no-dmi: 禁用 DMI/SMBIOS 读取器。
