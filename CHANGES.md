# Changes in Xenia Cullis

This document lists the main differences from upstream Xenia Canary, focusing on the default settings used by this fork.

---

## Readback Resolve

| Setting | Default | Description |
|---------|---------|-------------|
| `readback_resolve` | `deferred` | Avoids forcing the GPU to stall when delivering resolve results to the CPU. Higher performance than `fast` while still remaining correct. |
| `readback_resolve_deferred_lazy` | `true` | Further reduces remaining stalls in deferred mode. Only delivers readbacks when the GPU has fully completed the work on its own. |
| `readback_resolve_morph_formats_only` | `true` | Limits readbacks to the formats most commonly used by morph targets (`k_8_8_8_8` and `k_1_5_5_5`). Reduces unnecessary work. |

---

## CPU

| Setting | Default | Description |
|---------|---------|-------------|
| `inline_loadclock` | `true` | Caches the guest clock for faster access. |
| `elide_e0_check` | `true` | Skips certain memory access checks for better performance. |
| `enable_rmw_context_merging` | `true` | Merges read-modify-write sequences into more efficient x86-64 instructions. |
| `align_all_basic_blocks` | `true` | Aligns the start of basic blocks to 16 bytes. |
| `disable_prefetch_and_cachecontrol` | `true` | Disables legacy Xbox 360 prefetch instructions and prefers host defaults. |
| `enable_rdrand_ntdll_patch` | `true` | Patches ntdll so it does not use RDRAND for heap randomization. |
| `ignore_thread_priorities` | `true` | Ignores thread priority changes requested by the game. |
| `guard_indirect_call_targets` | `true` | Prevents calls into invalid memory regions. |
| `deadlock_event_watchdog` | `true` | Helps recover from certain deadlocks. |
| `cpu_starvation_mitigation` | `true` | Keeps the game's logic thread more active to reduce starvation issues. |
| `cpu` | `x64` | Forces the x64 backend. |

---

## GPU

| Setting | Default | Description |
|---------|---------|-------------|
| `gpu` | `d3d12` | Forces the Direct3D 12 backend. |
| `render_target_path_d3d12` | `rtv` | Uses RTV path for render targets. |
| `native_2x_msaa` | `true` | Prefers host 2x MSAA when available. |
| `native_stencil_value_output` | `true` | Allows pixel shaders to output stencil reference values. |
| `gamma_render_target_as_unorm16` | `false` | Disables higher gamma accuracy for better performance. |
| `gpu_clamp_fp10_edram_output` | `true` | Clamps fp10 pixel shader color output. |
| `d3d12_pipeline_creation_threads` | `0` | Uses single-threaded D3D12 pipeline creation (can reduce stutter on some systems). |
| `anisotropic_override` | `5` | Forces 16x anisotropic filtering. |

---

## Resolution & Post-Processing

| Setting | Default | Description |
|---------|---------|-------------|
| `draw_resolution_scale_x` | `2` | Renders at 2× horizontal resolution. |
| `draw_resolution_scale_y` | `2` | Renders at 2× vertical resolution. |
| `postprocess_antialiasing` | `fxaa` | Enables FXAA anti-aliasing. |
| `postprocess_scaling_and_sharpening` | `cas` | Uses CAS (Contrast Adaptive Sharpening) when scaling. |

---

## Audio / Input / Other

| Setting | Default | Description |
|---------|---------|-------------|
| `apu` | `sdl` | Uses SDL for audio (better cross-platform compatibility). |
| `hid` | `sdl` | Uses SDL for input (better cross-platform compatibility). |
| `discord` | `false` | Disables Discord Rich Presence overlay. |
| `flush_log` | `false` | Disables forced log flushing. |
| `log_level` | `error` | Only logs errors. |
| `log_to_stdout` | `false` | Disables logging to the console. |

---

**Note:** These defaults prioritize a balance of performance, visual quality, and practicality. Individual settings can still be changed in the config file if needed.