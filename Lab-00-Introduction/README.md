# Lab 00 — Introduction to ns-3 and NetAnim

Optional warm-up lab: confirm your ns-3.47 environment works, run a C++
simulation, capture its output, and view a NetAnim animation. It is provided as
preparation for the assessed labs.

- **Optional setup activity:** [docs/Lab-00-Instructions.md](docs/Lab-00-Instructions.md)
- **Outputs:** Optional setup-check evidence; not part of the required deliverables

## Prerequisites

A working ns-3.47 environment and NetAnim — see
[docs/environment.md](../docs/environment.md). No earlier lab is required.

## Files

| Path | What it is |
|---|---|
| `code/Lab0_Cpp_Hello.cc` | Minimal "Hello Simulator" program |
| `code/Lab0_Cpp_Anim.cc` | Two-node program that writes a NetAnim XML |
| [`docs/Lab0_Introduction_to_ns-3.pdf`](docs/Lab0_Introduction_to_ns-3.pdf) | Lab handout |
| `submission/` | Optional local folder for the setup-check outputs |

## Running

For the "Hello, Simulator!" part, follow Part 1 of the
[instructions](docs/Lab-00-Instructions.md). The output is printed to the
terminal only, so redirect it to a file yourself.

The animation program uses the standard workflow that every later lab also uses.
From the repository root, with `$NS3_DIR` set:

```bash
cp Lab-00-Introduction/code/Lab0_Cpp_Anim.cc "$NS3_DIR/scratch/"
cd "$NS3_DIR"
./ns3 build
./ns3 run scratch/Lab0_Cpp_Anim
```

It takes no arguments and writes
`$NS3_DIR/scratch/Lab0outputs/lab0_cpp_anim.xml`.

## Outputs

Open the XML in NetAnim to verify that the setup works. If useful, you may keep
the suggested evidence in `submission/` using the names in the
[setup checklist](docs/deliverables.md). These optional outputs are for your own
setup verification rather than the required lab presentation.

Problems: [docs/troubleshooting.md](../docs/troubleshooting.md).
