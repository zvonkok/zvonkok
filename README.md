<h1 align="center">Zvonko Kaiser</h1>

<p align="center">
  Systems engineer at <a href="https://www.nvidia.com">NVIDIA</a> &middot;
  <a href="https://github.com/kata-containers/community#architecture-committee">Kata Containers Architecture Committee</a> &middot;
  Toronto
</p>

<p align="center">
  <a href="https://github.com/zvonkok?tab=followers"><img alt="GitHub followers" src="https://img.shields.io/github/followers/zvonkok?style=flat-square&logo=github&label=followers&color=0366d6"></a>
  <img alt="Rust" src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white">
  <img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white">
  <img alt="Linux" src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black">
  <img alt="NVIDIA" src="https://img.shields.io/badge/NVIDIA-76B900?style=flat-square&logo=nvidia&logoColor=white">
</p>

<p align="center"><em>All work and no play makes Jack a dull boy, all play and no work makes Jack a mere toy.</em></p>

I build the layer where GPUs meet virtual machines and Kubernetes: confidential
computing for accelerators, VFIO/PCIe device passthrough into lightweight VMs,
and the Rust plumbing that makes it boot fast and stay small.

## What I work on

- **Confidential GPU computing** in [Kata Containers](https://github.com/kata-containers/kata-containers) and [Confidential Containers](https://github.com/confidential-containers): H100-class confidential-computing controls and the Kubernetes management pieces around them.
- **Device passthrough done right**: PCIe/VFIO enumeration, NVSwitch fabric configuration, and the Container Device Interface for runtimes.
- **Rust for the boot path**: [NVRC](https://github.com/NVIDIA/nvrc), a small init system for GPU microVMs, plus the libraries it is built from.
- **Kubernetes operator work** around the NVIDIA GPU Operator and its Kata and confidential-computing managers.

## Selected projects

| Project | What it is |
| --- | --- |
| [kata-containers/kata-containers](https://github.com/kata-containers/kata-containers) | Lightweight VMs that behave like containers. GPU and confidential-computing device support, Architecture Committee member. |
| [NVIDIA/nvrc](https://github.com/NVIDIA/nvrc) | Rust init system for NVIDIA confidential-computing microVMs. |
| [cncf-tags/container-device-interface-rs](https://github.com/cncf-tags/container-device-interface-rs) | Rust implementation of the Container Device Interface (CDI). |
| [kata-containers/pcilibs-rs](https://github.com/kata-containers/pcilibs-rs) | Linux PCI enumeration, VFIO driver matching and InfiniBand diagnostics in Rust. |
| [zvonkok/gpu-admin-tools-rs](https://github.com/zvonkok/gpu-admin-tools-rs) | GPU admin tooling, including confidential-computing controls for H100. |
| [zvonkok/fmclient](https://github.com/zvonkok/fmclient) | Fabric Manager client for configuring the NVSwitch fabric. |
| [zvonkok/perf-panacea](https://github.com/zvonkok/perf-panacea) | A tutorial on `perf` and BPF for performance profiling. |

## By the numbers

<p align="center">
  <img alt="GitHub summary" src="./header.svg">
</p>

<table align="center">
  <tr>
    <td valign="top"><img alt="Notable contributions" src="./notable.svg"></td>
    <td valign="top"><img alt="Achievements" src="./achievements.svg"></td>
  </tr>
  <tr>
    <td valign="top"><img alt="Most used languages" src="./languages.svg"></td>
    <td valign="top"><img alt="Repositories and lines of code" src="./repositories.svg"></td>
  </tr>
  <tr>
    <td valign="top"><img alt="Contribution calendar" src="./isocalendar.svg"></td>
    <td valign="top"><img alt="Coding habits" src="./habits.svg"></td>
  </tr>
  <tr>
    <td valign="top"><img alt="Recent activity and community" src="./activity.svg"></td>
    <td valign="top"><img alt="Issues and pull requests" src="./followup.svg"></td>
  </tr>
</table>

<p align="center">
  <sub>Cards refresh nightly via <a href="./.github/workflows/metrics.yml">GitHub Actions</a> using a <a href="./.github/metrics">patched build</a> of <a href="https://github.com/lowlighter/metrics">lowlighter/metrics</a>. They follow your light/dark theme.</sub>
</p>
