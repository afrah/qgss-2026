# Qiskit Global Summer School 2026 — my solutions

**These are my own solutions**, written while participating in the
[Qiskit Global Summer School 2026](https://quantum.cloud.ibm.com/learning/courses).

This repository is a **fork of the official course repository**,
[qiskit-community/qgss-2026](https://github.com/qiskit-community/qgss-2026). The lab
notebooks, the `utils/` helpers, the FAQ, and the per-lab READMEs under
`qgss_2026_main/` are IBM's course material; what I have added is the completed
exercise cells and the explanatory notes described below. All original material
remains under its upstream [LICENSE](qgss_2026_main/LICENSE).

The notebooks are kept in their executed state, with all outputs, plots, and
hardware results intact.

Every exercise cell has been annotated: each solution is preceded by a markdown
"Solution notes" section explaining the reasoning, and the code carries
line-level comments covering the non-obvious choices — endianness conventions,
qubit-layout constraints, why a particular mitigation flag is set explicitly
rather than via a resilience level, and so on.

> **The grader is retired.** The `qc_grader` package and its
> `grade_lab*_ex*` / `check_progress` endpoints were decommissioned along with
> QGSS 2026. Grader cells are left in place so each notebook still reads as the
> original assignment, but they will raise if re-executed. **The notebooks have
> not been re-run since the grader went offline** — the stored outputs are the
> originals from the graded submissions.

> **No credentials in this repository.** Every notebook obtains hardware access
> through `QiskitRuntimeService()`, which reads the account saved by
> `QiskitRuntimeService.save_account(...)` into `~/.qiskit/qiskit-ibm.json` —
> outside this repo. A handful of cells contain hardcoded IBM Quantum **job
> IDs**; those identify completed runs in a job history and are only usable by
> the account that submitted them. They are not secrets.

## Labs

| Lab | Title | Notebook(s) |
|-----|-------|-------------|
| [Lab 0](qgss_2026_main/lab-0/) | Welcome & Setup (not graded) | [QGSS2026_Lab0.ipynb](qgss_2026_main/lab-0/QGSS2026_Lab0.ipynb) |
| [Lab 1](qgss_2026_main/lab-1/) | Building Quantum Circuits for Real Hardware | [python](qgss_2026_main/lab-1/python/QGSS2026_Lab1.ipynb) · [cpp](qgss_2026_main/lab-1/cpp/QGSS2026_Lab1_cpp.ipynb) |
| [Lab 2](qgss_2026_main/lab-2/) | Noise, Backends, and Benchmarking in Qiskit | [QGSS2026_Lab2.ipynb](qgss_2026_main/lab-2/QGSS2026_Lab2.ipynb) |
| [Lab 3](qgss_2026_main/lab-3/) | Your New Tool For Quantum Advantage | [QGSS2026_Lab3.ipynb](qgss_2026_main/lab-3/QGSS2026_Lab3.ipynb) |
| [Lab 4](qgss_2026_main/lab-4/) | Towards Quantum Advantage | [4a](qgss_2026_main/lab-4/QGSS2026_Lab4a.ipynb) · [4b](qgss_2026_main/lab-4/QGSS2026_Lab4b.ipynb) · [4c](qgss_2026_main/lab-4/QGSS2026_Lab4c.ipynb) |

### What each lab covers

- **Lab 0** — environment setup, first circuits, the Qiskit primitives.
- **Lab 1** — transpilation for real hardware, in Python and via the C++ API.
- **Lab 2** — noise models, fake backends, heavy-hex vs. square-lattice
  topologies, and dynamic circuits with mid-circuit measurement and feedforward.
- **Lab 3** — the Samplomatic/annotation stack: twirling, noise learning,
  Pauli-Lindblad models, PNA and SLC. Hardware-only; the `*_JOB_ID` slots are
  unset.
- **Lab 4a** — the Framework for Quantum Advantage and the Quantum Advantage
  Tracker. Reading exercise, no hardware.
- **Lab 4b** — the partition problem via QAOA: QUBO → MaxCut → Ising, eight
  error-mitigation configurations across the Sampler and Estimator, Pauli
  Correlation Encoding (160 nodes on 11 qubits), and a 1600-node bonus.
- **Lab 4c** — Sample-based Quantum Diagonalization of N₂: the LUCJ ansatz,
  hand-built 52-qubit layouts, configuration recovery, and a classically
  augmented subspace.

## Repository layout

```
qgss-2026/
├── README.md                              this file
├── .gitignore                             credentials, caches, checkpoints
├── random_params_for_bonus.npy            random QAOA seed params for the Lab 4b bonus
└── qgss_2026_main/                        the forked course repository
    ├── FAQ.md                             course FAQ (labs, submission, setup)
    ├── LICENSE                            Apache 2.0, from upstream
    ├── .gitignore                         upstream's Python gitignore
    │
    ├── lab-0/                             Welcome & setup — not graded
    │   ├── README.md
    │   └── QGSS2026_Lab0.ipynb            76 cells
    │
    ├── lab-1/                             Building circuits for real hardware
    │   ├── python/                          solve either version, not both
    │   │   ├── README.md
    │   │   └── QGSS2026_Lab1.ipynb        93 cells
    │   └── cpp/
    │       ├── README.md
    │       ├── QGSS2026_Lab1_cpp.ipynb    110 cells
    │       ├── CMakeLists.txt             build for the Qiskit C extension
    │       └── compat/                    headers shimming the C API
    │           ├── quantumcircuit.hpp
    │           ├── statevector.hpp
    │           ├── target.hpp
    │           └── transpile.hpp
    │
    ├── lab-2/                             Noise, backends, benchmarking
    │   └── QGSS2026_Lab2.ipynb            136 cells
    │
    ├── lab-3/                             Your new tool for quantum advantage
    │   └── QGSS2026_Lab3.ipynb            244 cells
    │
    ├── lab-4/                             Towards quantum advantage
    │   ├── QGSS2026_Lab4a.ipynb           24 cells  — advantage frameworks
    │   ├── QGSS2026_Lab4b.ipynb           151 cells — QAOA partition problem
    │   └── QGSS2026_Lab4c.ipynb           87 cells  — SQD on N₂
    │
    └── utils/                             shared across labs
        ├── functions.py                   plotting and result-analysis helpers
        ├── numbers_large.npy              160 integers — Lab 4b section 3
        ├── numbers_bonus.npy              1600 integers — Lab 4b bonus
        ├── pretrained_parameters_small.npy   6-node QAOA params — Lab 4b section 1
        └── pretrained_parameters_pce.npy     PCE-ansatz params — Lab 4b section 3
```

Notes on a few entries:

- **`qgss_2026_main/`** is the upstream repository, vendored as a subdirectory
  rather than flattened, so the paths the notebooks use internally
  (`qgss_2026_main/utils/...`) resolve when a notebook is run from the repo root.
  That is also why several cells call `ls qgss_2026_main` — they are checking
  that the `utils` folder is reachable.
- **The `.npy` files are inputs, not results.** They hold pre-generated problem
  instances and pre-trained variational parameters so the labs are reproducible
  and so you can skip the expensive hardware training loops.
- **`random_params_for_bonus.npy`** sits at the repo root rather than in `utils/`
  because Lab 4b's bonus cell writes it there with a bare relative filename.
- **Notebook sizes** range from 72 KB (Lab 0) to 8.5 MB (Lab 4c); the bulk is
  base64-encoded plots and circuit diagrams in the stored outputs.

## Running these notebooks

Most labs need real QPU access and will not run end to end without it. To try
anyway:

1. Save your IBM Quantum account once, from a shell — never from a notebook cell:

   ```python
   from qiskit_ibm_runtime import QiskitRuntimeService
   QiskitRuntimeService.save_account(channel="ibm_quantum_platform", token="<your-token>")
   ```

   This writes `~/.qiskit/qiskit-ibm.json`, outside the repository.

2. Install the per-lab dependencies from the (commented-out) `%pip install`
   cells at the top of each notebook.

3. Skip or remove the grader cells — those endpoints no longer exist.

Labs 2 and 4a run without hardware. Lab 4c's classical portion (pyscf, CCSD, the
eigensolver) runs locally; only the sampling step needs a QPU, and that job's
results are retrieved by ID rather than resubmitted.
