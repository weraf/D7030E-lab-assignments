# Lab 03 — UAV Mesh and Ad-hoc Multi-hop Networks

Ad-hoc 802.11b without an access point: throughput over multiple hops, the effect
of payload size, TCP versus UDP, OLSR versus AODV, and hidden terminals.

- **Required work:** [docs/Lab-03-Instructions.md](docs/Lab-03-Instructions.md)
- **Include in the Canvas PDF:** [docs/deliverables.md](docs/deliverables.md)

## Prerequisites

A working ns-3.47 environment is required; the optional Lab 00 setup activity
can help you verify it. Lab 02 gives useful context for the hidden-terminal
part. Environment: [docs/environment.md](../docs/environment.md).

## Files

| Path | Used for (part numbering as in the instructions) |
|---|---|
| `code/Lab3_Cpp_Adhoc.cc` | Part 1 multi-hop UDP chain; Part 4 OLSR vs AODV |
| `code/Lab3_Cpp_PayloadSweep.cc` | Part 2 payload sweep over hop counts |
| `code/Lab3_Cpp_TCP.cc` | Part 3 TCP three-node chain |
| `code/Lab3_Cpp_Hidden.cc` | Part 5 hidden terminal, RTS/CTS off and on |
| [`docs/Lab3_ns-3_adhoc-1.pdf`](docs/Lab3_ns-3_adhoc-1.pdf), [reference paper](docs/PerformanceComparisonbetweenTCPandUDPProtocolsinDifferentSimulationScenarios.pdf) | Lab handout and reference paper |
| [`docs/background.md`](docs/background.md) | What each starter does and how throughput is computed (background reading) |
| `submission/` | Optional folder for working files used to prepare the Canvas PDF |

## Running

From the repository root, with `$NS3_DIR` set:

```bash
cp Lab-03-Adhoc/code/Lab3_Cpp_*.cc "$NS3_DIR/scratch/"
cd "$NS3_DIR"
./ns3 build
./ns3 run "scratch/Lab3_Cpp_Adhoc --numNodes=4 --pktSize=1200 --distance=200 --routing=olsr --seed=1"
```

| Argument | Programs | Meaning |
|---|---|---|
| `--numNodes` | Adhoc | Nodes in the chain (≥ 3) |
| `--nodes`, `--pkts`, `--seeds` | PayloadSweep | Comma-separated lists, e.g. `--nodes=3,4,5,6 --pkts=300,700,1200 --seeds=1,2` |
| `--pktSize` | Adhoc, TCP, Hidden | UDP payload / TCP segment size in bytes |
| `--distance` | all | Spacing between nodes in metres |
| `--routing` | Adhoc | `olsr` or `aodv` |
| `--enableRtsCts` | Hidden | `0` off, `1` on |
| `--seed` | Adhoc, TCP, Hidden | RNG run number |
| `--appRate` | all | Offered application data rate, e.g. `1Mbps` |
| `--csv` | PayloadSweep, TCP, Hidden | Also write the results to this path (`Lab3_Cpp_Hidden` appends, the other two overwrite) |
| `--enableAnim`, `--enablePcap` | all | Write NetAnim XML / PCAP traces (off by default) |

Multi-hop needs a routing protocol; `Lab3_Cpp_Adhoc` uses OLSR unless you pass
`--routing=aodv`. Each chain run first gives the routing protocol 30 simulated
seconds to converge and then sends for 9 seconds — that 9-second window is what
the reported throughput is measured over.

## Outputs

Throughput is printed per flow to stdout. Animation and PCAP files are written
under `$NS3_DIR/scratch/Lab3outputs/`; a `--csv` file goes to the path you give,
relative to `$NS3_DIR`. Keep what you need in `submission/` under the suggested
working names in [docs/deliverables.md](docs/deliverables.md), then curate the
required results into the Canvas PDF.

Problems: [docs/troubleshooting.md](../docs/troubleshooting.md).
