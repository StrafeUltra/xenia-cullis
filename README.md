<p align="center">
    <a href="https://github.com/StrafeUltra/xenia-cullis/tree/canary_experimental/assets/icon">
        <img height="256px" src="https://raw.githubusercontent.com/StrafeUltra/xenia-cullis/refs/heads/canary_experimental/assets/icon/icon.ico" />
    </a>
</p>

<h1 align="center">Xenia Cullis</h1>

Xenia Cullis is an experimental fork of Xenia Canary.

## Goals

This fork aims to bring performance focused improvements (especially around expensive options such as readback resolve) while staying as up to date as possible with upstream Xenia Canary.

In addition to those optimizations, experimental options will be added over time to try improving areas where the emulator still falls short.

The long-term goal is to keep the fork usable with the full range of games so that a single build can be used instead of maintaining multiple versions.
That said, development focus will likely center on out-of-the box compatibility with a smaller set of titles.

## Changes

A detailed list of the default setting changes in this fork can be found in [CHANGES.md](CHANGES.md).

## Disclaimer

The goal of this project is to experiment, research, and educate on the topic
of emulation of modern devices and operating systems. **It is not for enabling
illegal activity**. All information is obtained via reverse engineering of
legally purchased devices and games and information made public on the internet
(you'd be surprised what's indexed on Google...).

This fork is based on Xenia / Xenia Canary and remains under the original 3-Clause BSD license.
Large parts of the performance-related work (particularly around readback resolve) originated from Gummi's fork and were integrated here: https://github.com/StrafeUltra/xenia-cullis/commit/18516638bee068960fcc8d49f28d08f354951767
Credit for that work belongs to Gummi.

Any original contributions I make to this fork are also released under the same 3-Clause BSD license.
