<h1 align="center">Zvonko Kaiser</h1>

<p align="center">
  Systems engineer, <a href="https://www.nvidia.com">NVIDIA</a> &middot;
  <a href="https://github.com/kata-containers/community#architecture-committee">Kata Containers Architecture Committee</a> &middot;
  <a href="https://github.com/confidential-containers">Confidential Containers</a> &middot;
  Toronto
</p>

<p align="center">
  <a href="https://github.com/zvonkok?tab=followers"><img alt="GitHub followers" src="https://img.shields.io/github/followers/zvonkok?style=flat-square&logo=github&label=followers&color=0366d6"></a>
  <img alt="Rust" src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white">
  <img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img alt="Linux" src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black">
  <img alt="QEMU" src="https://img.shields.io/badge/QEMU-FF6600?style=flat-square&logo=qemu&logoColor=white">
  <img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white">
  <img alt="NVIDIA" src="https://img.shields.io/badge/NVIDIA-76B900?style=flat-square&logo=nvidia&logoColor=white">
</p>

GPUs inside lightweight and confidential VMs: device passthrough, guest boot
path, runtime integration, and the Kubernetes plumbing on top.

## Technical focus

**GPU passthrough into Kata Containers** ([kata-containers/kata-containers](https://github.com/kata-containers/kata-containers), Go and Rust)
- VFIO and IOMMUFD device handling in the runtime, including NVSwitch passthrough by separating the IOMMUFD path from legacy VFIO groups, and keeping the pause container free of cold-plugged devices.
- PCIe topology work in QEMU: root port and BAR reserve sizing, PPCIE mode for DGX/HGX class systems, HGX B-series kernel enablement.
- NUMA support across agent, QEMU and guest kernel so multi-GPU guests see the host topology.
- Vendor-agnostic CDI annotation handling in the runtime; the agent consumes CDI specs through the Rust CDI crate.
- The `nvgpu` build pipeline: guest kernel with module signing (amd64 and arm64), measured rootfs, decoupled kernel and rootfs artifacts, driver and CUDA bundling from local or remote repos, TDX kernel command line, and the NVIDIA GPU CI/CD lanes.

**NVRC: a Rust init for GPU microVMs** ([NVIDIA/nvrc](https://github.com/NVIDIA/nvrc))
- Minimal PID 1 that brings up the NVIDIA driver stack inside the guest: mode auto-detection from hardware topology, NVLink handling for single-GPU VMs, configfs/filesystem setup, daemon synchronization.
- Hardened exec path, byte-reproducible release builds enforced in CI, fuzz targets for kernel parameter and mount parsing, 90% per-file line coverage gate, boot-time logging of the binary's SHA-256.

**Rust systems libraries**
- [cncf-tags/container-device-interface-rs](https://github.com/cncf-tags/container-device-interface-rs): CDI spec implementation with v1.1.0 parity, opt-in spec validation, lean dependency set, published on crates.io, end-to-end tested against the kata-agent.
- [kata-containers/pcilibs-rs](https://github.com/kata-containers/pcilibs-rs): sysfs PCI enumeration, VFIO and IOMMUFD cdev discovery, NVLink topology discovery, hardware classification for confidential-computing capable GPUs (H100 through Rubin).
- [kata-containers/cgroups-rs](https://github.com/kata-containers/cgroups-rs) contributions, and [zvonkok/gpu-admin-tools-rs](https://github.com/zvonkok/gpu-admin-tools-rs) for H100 confidential-computing mode controls.

**Kubernetes and NVIDIA operators** (Go)
- [NVIDIA/sandbox-device-plugin](https://github.com/NVIDIA/sandbox-device-plugin): CDI spec generation for heterogeneous GPU nodes, NVSwitch discovery via go-nvlib.
- [NVIDIA/k8s-cc-manager](https://github.com/NVIDIA/k8s-cc-manager) (PPCIE mode), [NVIDIA/k8s-kata-manager](https://github.com/NVIDIA/k8s-kata-manager), [NVIDIA/gpu-operator](https://github.com/NVIDIA/gpu-operator) operand updates.

**Older work**: [perf and BPF profiling tutorial](https://github.com/zvonkok/perf-panacea), [pagemap](https://github.com/zvonkok/pagemap) (virtual to physical page mapping from userspace), [GPU mean-shift image segmentation](https://github.com/zvonkok/gpu-meanshift-segmentation), [large-number prime factorization](https://github.com/zvonkok/prime-factorization).

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
