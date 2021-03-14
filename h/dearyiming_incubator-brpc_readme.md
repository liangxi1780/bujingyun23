[中文版](README_cn.md)

[![Build Status](https://travis-ci.org/apache/incubator-brpc.svg?branch=master)](https://travis-ci.org/apache/incubator-brpc)

# ![brpc](docs/images/logo.png)

An industrial-grade RPC framework used throughout [Baidu](http://u.720life.cn/g/20ba59c2f50270246246f1b9470a746836852146f8cad44f7244bc4a9f1502df35222a5d2926067978b428bea57337c705a6caf2bdbc41c1ad1fa2c9ee93c662  with 1,000,000+ instances(not counting clients) and thousands kinds of services, called "**baidu-rpc**" inside Baidu. Only C++ implementation is opensourced right now.

You can use it to:
* Build a server that can talk in multiple protocols (**on same port**), or access all sorts of services
  * restful http/https, [h2](http://u.720life.cn/g/50aa2f6c6fb69b2f37d99d490db052663f56f489383fc68feef756be4e9b87922e6445e234cab22f7d078af05c251d469f55b87e4244c058ad81f48dba84fc31  using http/h2 in brpc is much more friendly than [libcurl](http://u.720life.cn/g/c9fa89c66db4bfd512eaa45e319ce993c637d668c26d07dcc7783ae15ac872ad  Access protobuf-based protocols with HTTP/h2+json, probably from another language.
  * [redis](docs/en/redis_client.md) and [memcached](docs/en/memcache_client.md), thread-safe, more friendly and performant than the official clients.
  * [rtmp](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304602ddbdb64fe49b5a25895836fab560b4a45ac89bf66a1fba5b3be4c43d020aed7faff681f2c134eb4ca1ce7675a93bebe09ee54288b0077581391b0c029a87656d320007a5c4960e21449d3ac6ca098da18bbe74d07772f5e0f46406dd505646419ec4d29b0124726c2137f254c59a246bbc5412edd8c78afdcdccd584d4dcc756ea318be0e627fcb7fc4bccc575bf39268ce8efc55c9c10271d8f6a894525cd  for building [streaming services](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a20e015f383780a5ab7667560115462d1d57cac0b579c02610330e3ae992d3e3 
  * hadoop_rpc (may be opensourced)
  * [rdma](http://u.720life.cn/g/dbf1195f8a53209e138d24666db0663625a3b25912f6e94dfba4941cefcaf2346df27ecf78cc0f01c2ca8b6ed32567053525aaad813cbbbb5c5f49e573ad62d9)  support (will be opensourced)
  * [thrift](docs/en/thrift.md) support,  thread-safe, more friendly and performant than the official clients.
  * all sorts of protocols used in Baidu: [baidu_std](docs/cn/baidu_std.md), [streaming_rpc](docs/en/streaming_rpc.md), hulu_pbrpc, [sofa_pbrpc](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046413bd52b436695ed434696b0a422ed895292244fe3e4ac704fcec55d40677a0b  nova_pbrpc, public_pbrpc, ubrpc and nshead-based ones.
  * Build [HA](http://u.720life.cn/g/dbf1195f8a53209e138d24666db066362235b359e9ac86dced490cc679fd60e887b15d99f285feab1e87bcaf90956c60)  distributed services using an industrial-grade implementation of [RAFT consensus algorithm](http://u.720life.cn/g/ccc2c0cb980f042c691b6caa35ee7cfb63376c2be0d3439eb8f1013963b7a116)  which is opensourced at [braft](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464643c6f30047423a873d4b020660b478) 
* Servers can handle requests [synchronously](docs/en/server.md) or [asynchronously](docs/en/server.md#asynchronous-service).
* Clients can access servers [synchronously](docs/en/client.md#synchronus-call), [asynchronously](docs/en/client.md#asynchronous-call), [semi-synchronously](docs/en/client.md#semi-synchronous-call), or use [combo channels](docs/en/combo_channel.md) to simplify sharded or parallel accesses declaratively.
* Debug services [via http](docs/en/builtin_service.md), and run  [cpu](docs/cn/cpu_profiler.md), [heap](docs/cn/heap_profiler.md) and [contention](docs/cn/contention_profiler.md) profilers.
* Get [better latency and throughput](docs/en/overview.md#better-latency-and-throughput).
* [Extend brpc](docs/en/new_protocol.md) with the protocols used in your organization quickly, or customize components, including [naming services](docs/cn/load_balancing.md#命名服务) (dns, zk, etcd), [load balancers](docs/cn/load_balancing.md#负载均衡) (rr, random, consistent hashing)

# Try it!

* Read [overview](docs/en/overview.md) to know where brpc can be used and its advantages.
* Read [getting started](docs/cn/getting_started.md) for building steps and play with [examples](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a371571601ee1aad2c7c908e188f5286d9dfd483ebc13c50e65a0f875e43a66601c625e836f604c69d26900ab5e1bbc 
* Docs:
  * [Performance benchmark](docs/cn/benchmark.md)
  * [bvar](docs/en/bvar.md)
    * [bvar_c++](docs/cn/bvar_c++.md)
  * [bthread](docs/cn/bthread.md)
    * [bthread or not](docs/cn/bthread_or_not.md)
    * [thread-local](docs/cn/thread_local.md)
    * [Execution Queue](docs/cn/execution_queue.md)
  * Client
    * [Basics](docs/en/client.md)
    * [Error code](docs/en/error_code.md)
    * [Combo channels](docs/en/combo_channel.md)
    * [Access http/h2](docs/en/http_client.md)
    * [Access gRPC](docs/en/http_derivatives.md#h2grpc)
    * [Access thrift](docs/en/thrift.md#client-accesses-thrift-server) 
    * [Access UB](docs/cn/ub_client.md)
    * [Streaming RPC](docs/en/streaming_rpc.md)
    * [Access redis](docs/en/redis_client.md)
    * [Access memcached](docs/en/memcache_client.md)
    * [Backup request](docs/en/backup_request.md)
    * [Dummy server](docs/en/dummy_server.md)
  * Server
    * [Basics](docs/en/server.md)
    * [Serve http/h2](docs/en/http_service.md)
    * [Serve gRPC](docs/en/http_derivatives.md#h2grpc)
    * [Serve thrift](docs/en/thrift.md#server-processes-thrift-requests)
    * [Serve Nshead](docs/cn/nshead_service.md)
    * [Debug server issues](docs/cn/server_debugging.md)
    * [Server push](docs/en/server_push.md)
    * [Avalanche](docs/cn/avalanche.md)
    * [Auto ConcurrencyLimiter](docs/cn/auto_concurrency_limiter.md)
    * [Media Server](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a20e015f383780a5ab7667560115462dd5fce09203634a6f66d521d2c60665cb) 
    * [json2pb](docs/cn/json2pb.md)
  * [Builtin Services](docs/en/builtin_service.md)
    * [status](docs/en/status.md)
    * [vars](docs/en/vars.md)
    * [connections](docs/cn/connections.md)
    * [flags](docs/cn/flags.md)
    * [rpcz](docs/cn/rpcz.md)
    * [cpu_profiler](docs/cn/cpu_profiler.md)
    * [heap_profiler](docs/cn/heap_profiler.md)
    * [contention_profiler](docs/cn/contention_profiler.md)
  * Tools
    * [rpc_press](docs/cn/rpc_press.md)
    * [rpc_replay](docs/cn/rpc_replay.md)
    * [rpc_view](docs/cn/rpc_view.md)
    * [benchmark_http](docs/cn/benchmark_http.md)
    * [parallel_http](docs/cn/parallel_http.md)
  * Others
    * [IOBuf](docs/en/iobuf.md)
    * [Streaming Log](docs/en/streaming_log.md)
    * [FlatMap](docs/cn/flatmap.md)
    * [brpc外功修炼宝典](docs/cn/brpc_intro.pptx)(training material)
    * [A tutorial on building large-scale services](docs/en/tutorial_on_building_services.pptx)(training material)
    * [brpc internal](docs/en/brpc_internal.pptx)(training material)
  * RPC in depth
    * [New Protocol](docs/en/new_protocol.md)
    * [Atomic instructions](docs/en/atomic_instructions.md)
    * [IO](docs/en/io.md)
    * [Threading Overview](docs/en/threading_overview.md)
    * [Load Balancing](docs/cn/load_balancing.md)
    * [Locality-aware](docs/cn/lalb.md)
    * [Consistent Hashing](docs/cn/consistent_hashing.md)
    * [Memory Management](docs/cn/memory_management.md)
    * [Timer keeping](docs/cn/timer_keeping.md)
    * [bthread_id](docs/cn/bthread_id.md)
  * Use cases inside Baidu
    * [百度地图api入口](docs/cn/case_apicontrol.md)
    * [联盟DSP](docs/cn/case_baidu_dsp.md)
    * [ELF学习框架](docs/cn/case_elf.md)
    * [云平台代理服务](docs/cn/case_ubrpc.md)

# Contribute code
Please refer to [here](CONTRIBUTING.md).

# Feedback and Getting involved
* Report bugs, ask questions or give suggestions by [Github Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c0001bca31ae58bae1a9ea2d5840c8aa253ced3d58a18c8979df911c16eeb089) 
* Subscribe mailing list(dev-subscribe@brpc.apache.org) to get updated with the project



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)