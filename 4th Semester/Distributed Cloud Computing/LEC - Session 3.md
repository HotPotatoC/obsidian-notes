Class: [[COMP6710001 - Distributed Cloud Computing]]
Session: 3
Topics: 
- Performance Security, and Energy Efficiency
- Software Environments for Distributed Systems and Clouds
Date: 2023-03-01
Lecturer: [[D6667 - SAID ACHMAD, S.Kom., M.Kom]]

# Performance Metrics and Scalability Analysis

**Performance Metrics:**
- CPU Speed: MHz or GHz, SPEC benchmarks like SPECINT
- Network Bandwidth: Mbps or Gbps
- System throughput: MIPS, TFlops (tera floating-point operations per second), TPS (transactions per second), IOPS (IO operations per second)
- Other metrics: Response time, netwrok latency, system availability

**Scalability:**
- Scalability is the ability of a system to handle growing amount of work in a capable/efficient manner or its ability to be enlarged to accomodate that growth.
- For example, it can refer to the capability of a system to increase a total throughput under an increased load when resources (typically hardware) are added.

# Types of Scalability

**Horizontal Scaling**
To scale horizontally (or scale out) means to add more nodes to a system, such as adding a new computer to a distributed software application. An example might be scaling out from one Web server system to three.

**Vertical Scaling**
To scale vertically (or **scale up**) means to add resources to a single node in a system, typically involving the addition of CPUs or memory to a single computer.

# Amdahl's law

Amdahl's law is a formula which gives the theoretical speedup in latency of the execution of a task at fixed workload that can be expected of a system whose resources are improved

It is typically cheaper to add a new node to a system in order to achieve improved performance than to perform performance tuning to improve the capacity that each node can handle. But this approach can have diminishing returns as indicated by Amdahl's law

Let
$S$ = Speedup
$T$ = Time
$\alpha$ = Fraction of $\alpha$ of the code must be executed sequentially (*sequential bottleneck*)
$n$ = number of processor/nodes
$$
S = \frac{1}{\alpha + (\frac{1- \alpha}{n})}
$$

The maximum of speedup of $n$ is achievable only when $\alpha = 0$, i.e. the entire program is parallelizable.

## Example

Suppose 70% of a program can be sped up if parallelized and run on multiple CPUs instead of one CPU

- N = 4 CPU
$$
S = \frac{1}{0.3 + (\frac{1- 0.3}{4})} = 2.105
$$

- N = 8 CPU
$$
S = \frac{1}{0.3 + (\frac{1- 0.3}{8})} = 2.581
$$

Double the processing power has only improved the speedup by roughly one-fifth. Therefore, throwing in more hardware is not necessarily the optimal approach.

# Fault Tolerance and System Availability

High availability (HA) is desired in all clusters, grids P2P networks, and cloud systems. A system is highly available if it has a long Mean Time to Failure (MTTF) and a short Mean Time to Repair (MTTR).

System Availability = $\frac{MTTF}{MTTF + MTTR}$

In general, as a distributed system increases in size, availability decreases due to a higher chance of failure and a difficulty in isolating failures.