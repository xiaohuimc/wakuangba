## Ubuntu CPU

### 1. 编译程序

```shell
sudo apt-get install git build-essential cmake libuv1-dev libmicrohttpd-dev libssl-dev libhwloc-dev
git clone https://gitee.com/wakuangba/xmrig.git
cd xmrig
mkdir build
cd build
cmake ..
make
```

#### gcc 7.1

您可以选择使用gcc 7来提高性能。
如果`add-apt-repository`找不到命令，请先安装`software-properties-common`。

运行cmake时手动指定C和C ++编译器：

```shell
cmake .. -DCMAKE_C_COMPILER = gcc-7 -DCMAKE_CXX_COMPILER = g ++  -  7
```

#### 其他CMake选项

- -DUV_LIBRARY=/usr/lib/x86_64-linux-gnu/libuv.a` 使用静态libuv版本。
- [更多选项](#qi-ta-cmake-xuan-xiang-1)



### 2. 执行程序

```shell
chmod +x xmrig
.\xmrig -o software.xmrpool.me:443 -u 钱包地址 -p x -k
```

* [更多选项](#xuan-xiang)


## CentOS CPU

### 1. 编译程序

```shell
sudo yum install -y epel-release
sudo yum install -y git make cmake gcc gcc-c++ libstdc++-static libmicrohttpd-devel libuv-static
git clone https://gitee.com/wakuangba/xmrig.git
cd xmrig
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release -DUV_LIBRARY=/usr/lib64/libuv.a
make
```

### 2.运行程序

```shell
chmod +x xmrig
.\xmrig -o software.xmrpool.me:443 -u 钱包地址 -p x -k
```

#### 选项

```shell
  -a, --algo=ALGO               指定要使用的算法
                                  cn/r, cn/2, cn/1, cn/0, cn/double, cn/half, cn/fast,
                                  cn/rwz, cn/zls, cn/xao, cn/rto, cn/gpu,
                                  cn-lite/1,
                                  cn-heavy/xhv, cn-heavy/tube, cn-heavy/0,
                                  cn-pico,
                                  rx/wow, rx/loki
  -o, --url=URL                 指定矿池地址
  -O, --userpass=U:P            用户名:密码
  -u, --user=USERNAME           矿池用户名
  -p, --pass=PASSWORD           矿池密码
      --rig-id=ID               矿池统计的标识符（需要矿池支持）
  -t, --threads=N               矿工线程数
  -v, --av=N                    算法变化，0自动选择
  -k, --keepalive               发送keepalived数据包以防止超时（需要矿池支持）
      --nicehash                启用nicehash.com支持
      --tls                     启用SSL / TLS支持（需要矿池支持）
      --tls-fingerprint=F       池TLS证书指纹，如果设置为启用严格证书固定
      --daemon                  使用守护进程RPC代替池进行单独挖掘
      --daemon-poll-interval=N  守护程序轮询间隔（以毫秒为单位）（默认值：1000）
  -r, --retries=N               切换到备份服务器之前重试的次数（默认值：5）
  -R, --retry-pause=N           重试之间暂停的时间（默认值：5）
      --cpu-affinity            设置CPU核心的进程亲和性，核心0和1的掩码0x3
      --cpu-priority            设置进程优先级（0空闲，2正常到5最高）
      --no-huge-pages           禁用大页面支持
      --no-color                禁用彩色输出
      --donate-level=N          捐赠水平，默认5％（100分钟内5分钟）
      --user-agent              为矿池设置自定义用户代理字符串
  -B, --background              后台运行矿工
  -c, --config=FILE             加载JSON格式的配置文件
  -l, --log-file=FILE           将所有输出记录到文件中
      --asm=ASM                 ASM优化，可能的值：auto，none，intel，ryzen，bulldozer。
      --print-time=N            每N秒打印一次哈希值报告
      --api-worker-id=ID        API的自定义worker-id
      --api-id=ID               API的自定义实例ID
      --http-enabled            启用HTTP API
      --http-host=HOST          绑定HTTP API的主机（默认值：127.0.0.1）
      --http-port=N             HTTP API的绑定端口
      --http-access-token=T     HTTP API的访问令牌
      --http-no-restricted      启用对HTTP API的完全远程访问（仅限访问令牌集）
      --randomx-init=N          线程计数初始化RandomX数据集
      --randomx-no-numa         禁用对RandomX的NUMA支持
      --export-topology         将hwloc拓扑导出到XML文件并退出
      --dry-run                 测试配置并退出
  -h, --help                    显示此帮助并退出
  -V, --version                 输出版本信息并退出
```

#### 其他CMake选项

- `-DWITH_LIBCPUID=OFF`禁用libcpuid。此后CPU的自动配置将非常有限。
- `-DWITH_AEON=OFF` 禁用CryptoNight-Lite算法和所有派生变体。
- `-DWITH_SUMO=OFF` 禁用CryptoNight-Heavy算法和所有派生变体。
- `-DWITH_CN_PICO=OFF` 禁用CryptoNight-Pico算法。
- `-DWITH_CN_GPU=OFF` 禁用CryptoNight-GPU算法。
- `-DWITH_HTTPD=OFF` 禁用内置的http服务器和API。
- `-DWITH_DEBUG_LOG=ON` 启用调试日志输出。
- `-DWITH_TLS=OFF` 禁用SSL / TLS支持。
- `-DWITH_ASM=OFF`禁用汇编语言支持。它将大大减缓`cn/2`基于算法，包括`cn/r`。
- `-DWITH_EMBEDDED_CONFIG=ON`启用内部嵌入式JSON配置[＃957](https://github.com/xmrig/xmrig/issues/957#issuecomment-468890667)。
- `-DBUILD_STATIC=ON`添加链接器标志`-static`。



