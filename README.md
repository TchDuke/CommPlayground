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
manual — [Руководство.md](Руководство.md). The screenshots show what the
windows actually look like; the same text in Russian follows below.

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

1,4M in total. Its own checks: Приёмка: 239 проверок, отказов 0, пропущено 1 (нужен каталог разработки).

Built on 07.09.2026.

<div align="center">— • —</div>

# CommPlayground

**Полигон модемов и каналов.** Соберите тракт — модем, канал, приёмник, —
прогоните через него кадр или целый текст и посмотрите, что получилось:
созвездие, спектр, осциллограмму и замеренную вероятность ошибки **рядом с
теоретической кривой**. Принятый текст показывается с **красными ошибочными
местами**, а сигнал можно **послушать**.

![CommPlayground](Screenshots/созвездие.png)

| Модем | |
|---|---|
| **QAM** | 4 … 1024 точки с кодом Грея, без кода |
| **TCM** | решётчатая кодированная модуляция Унгербёка с мягким Витерби |
| **BPSK** | настоящий полосовой тракт: несущая, петля Костаса, захват по преамбуле, формирование RRC |
| **OFDM** | поднесущие, циклический префикс, пилоты |

Каналы: АБГШ, плоские релеевские замирания, многолучёвый — с эквалайзером,
который можно выключить и увидеть, что он делал.

Как всем этим пользоваться — **[Руководство.md](Руководство.md)**.

## Запуск

```sh
./commplayground                 окно
./commplayground проект.cpg      окно с загруженным проектом
./commplayground --selftest      внутренние проверки, без окна
```

Нужен Linux x86-64 и SDL2. Рядом с бинарём должен лежать каталог `assets` —
из него берётся шрифт. Каталог настроек подменяется `COMM_CONFIG_DIR`.

## Ради чего это

|  |  |
|---|---|
| ![BER](Screenshots/ber-tcm.png) | ![текст](Screenshots/текст.png) |
| **Выигрыш кодирования, который видно, а не берут на веру.** Синим — замер кодированной модуляции, красным — некодированная QAM той же скорости. Ниже ~13 дБ код ПРОИГРЫВАЕТ: лишние точки созвездия ближе друг к другу. Выше — кривая уходит вниз. | **Свой текст через тракт.** Впишите, нажмите «Передать» — он пойдёт той же дорогой, на которой меряется BER. Ошибки вернутся красными, а сигнал можно послушать: передатчик, канал, выход эквалайзера. |

В `Examples/` лежит 5 проектов — по одному на интересный случай; у каждого в
первых строках сказано, зачем он и на что смотреть. Файл проекта — обычный
текст: модем, настройки и само сообщение.

## Лицензия

MIT — [LICENSE](LICENSE). Канонический текст MIT говорит о «программе **и
сопутствующих файлах документации**», поэтому руководство, снимки экрана и
проекты-примеры — на тех же условиях.

Всего 1,4M. Его собственная приёмка: Приёмка: 239 проверок, отказов 0, пропущено 1 (нужен каталог разработки).

Собрано 07.09.2026.
