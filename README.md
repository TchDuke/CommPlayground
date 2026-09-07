# CommPlayground

**A playground for modems and channels.** Assemble a link — modem, channel,
receiver — push a frame or a whole text through it, and see what came out: the
constellation, the spectrum, the waveform, and the measured bit error rate
**next to the theoretical curve**. The received text is shown with the wrong
places **in red**, and the signal can be **listened to**.

![CommPlayground](Screenshots/созвездие.png)

| Modem | |
|---|---|
| **QAM** | 4 … 1024 points with Gray mapping, uncoded |
| **TCM** | Ungerboeck trellis-coded modulation with a soft Viterbi decoder |
| **BPSK** | a real passband link: carrier, Costas loop, preamble acquisition, RRC shaping |
| **OFDM** | subcarriers, cyclic prefix, pilots |

Channels: AWGN, flat Rayleigh fading, multipath — with an equaliser that can be
switched off to see what it was doing.

**Note on language:** the program's interface is **in Russian**, and so is the
manual — [Руководство.md](Руководство.md). This page is the only English text
here; the screenshots show what the windows actually look like.

## Running it

```sh
./commplayground                 the window
./commplayground project.cpg     the window with a project loaded
./commplayground --selftest      internal checks, no window
```

Linux x86-64 and SDL2. The `assets` directory must sit beside the binary — the
font is taken from it. `COMM_CONFIG_DIR` overrides where settings are kept.

## What it is for

|  |  |
|---|---|
| ![BER](Screenshots/ber-tcm.png) | ![text](Screenshots/текст.png) |
| **The coding gain, seen rather than believed.** Blue is the measurement for trellis-coded modulation, red the uncoded QAM of the same data rate. Below ~13 dB the code loses — the extra constellation points sit closer together; above it, the curve dives. | **Your own text through the link.** Type it, press "Передать", and it travels the same path the error rate is measured on. Wrong characters come back red — and the signal can be played: the transmitter, the channel, the equaliser output. |

`Examples/` holds 5 ready projects, one per interesting case; each says in its
first lines what it is for and what to look at. A project file is plain text —
the modem, the settings and the message itself.

## License

MIT — see [LICENSE](LICENSE). The MIT text covers "the Software **and
associated documentation files**", so the manual, the screenshots and the
example projects are under the same terms.

1,4M in total. The binary is stripped, 868K; its own checks: Приёмка: 239 проверок, отказов 0, пропущено 1 (нужен каталог разработки).

Built on 07.09.2026.
