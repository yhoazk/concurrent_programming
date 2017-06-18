# concurrent_programming
Concurrent Programming learning path




### Concurrent vs Parallel

According to [Linux Magazine](http://www.linux-mag.com/id/7411/)

**Concurrency:** A concurrent program or algorithm is one where operations can
occur at the same time. For instance, a simple integration, where numbers are
summed over an interval. The interval can be broken into many concurrent sums
of smaller sub-intervals. **Concurrency is a property of the program, and
parallel excecution is a property of the machine**


#### From [SO](https://stackoverflow.com/a/3982782/6626231)

Concurrent programming regards operations that appear to overlap and is primarily concerned with the complexity that arises due to non-deterministic control flow. The quantitative costs associated with concurrent programs are typically both throughput and latency. Concurrent programs are often IO bound but not always, e.g. concurrent garbage collectors are entirely on-CPU. The pedagogical example of a concurrent program is a web crawler. This program initiates requests for web pages and accepts the responses concurrently as the results of the downloads become available, accumulating a set of pages that have already been visited. Control flow is non-deterministic because the responses are not necessarily received in the same order each time the program is run. This characteristic can make it very hard to debug concurrent programs. Some applications are fundamentally concurrent, e.g. web servers must handle client connections concurrently. Erlang is perhaps the most promising upcoming language for highly concurrent programming.

Parallel programming concerns operations that are overlapped for the specific goal of improving throughput. The difficulties of concurrent programming are evaded by making control flow deterministic. Typically, programs spawn sets of child tasks that run in parallel and the parent task only continues once every subtask has finished. This makes parallel programs much easier to debug. The hard part of parallel programming is performance optimization with respect to issues such as granularity and communication. The latter is still an issue in the context of multicores because there is a considerable cost associated with transferring data from one cache to another. Dense matrix-matrix multiply is a pedagogical example of parallel programming and it can be solved efficiently by using Straasen's divide-and-conquer algorithm and attacking the sub-problems in parallel. Cilk is perhaps the most promising language for high-performance parallel programming on shared-memory computers (including multicores).
