# Projekt Umetna inteligenca v

# avtonomni vožnji

Ajda Lašič, Mario Panzov, Niko Gorjan

## Tehnična dokumentacija

### Opis projekta

Za projekt Umetna inteligenca v avtonomni vožnji smo si zadali osnovno nalogo, da
pripeljemo avtomobilček iz labirinta. Idejo smo nato nadgradili z ciljem, da avtomobilček iz
labirinta s sabo pripelje še tarčo – v našem primeru osebo. Uporabnik ali igralec lahko izbira
med večimi načini vožnje avtomobilčka. V kolikor želi avtomobilček nadzirati sam, lahko to
počne na tri načine. Avtomobilček lahko nadzira s tipkami, z STM ploščico ali preko kamere.
Lahko pa avtomobilčku pusti, da se iz labirinta zapelje sam.

### Gradniki projekta

Za izvedbo projekta smo identificirali tri večje gradnike.

AirSim simulator v Unity okolju
AirSim je simulator vožnje za različna vozila. Zgrajen je na UnrealEngine, vključuje tudi
eksperimetalno izdajo na platformi Unity. Mi smo si za izdelavo projekta izbrali okolje Unity.
Uporabljena tehnologija:

- AirSim 1.3.1 Windows
- Unity 2020.3.2 3 f
- C# 9. 0
V Unity AirSim okolju ne uporabljamo drugih knjižnic. C# knjižnice uporabljene v projektu so
vključene v namestitev C# jezika.

Python vozlišče in YOLOv5 algoritem
Za komunikacijo med Unity okoljem in STM ploščico smo ustvarili Python vozlišče. Vozlišče s
ploščico komunicira preko serijskih vrat, z simulatorjem pa preko vtičnika.
Z implementacijo v jeziku Python smo omogočili tudi nadziranje avtomobilčka s kamero – to
počnemo s algoritmom YOLOv5 za prepoznavanje objektov na sliki.
Uporabljene tehnologije:

- Python 3.7.
- Airsim 1.5.
- Torch 1.10.1+cu
- Torchvision 0.11.2+cu
- Torchaudio 0.10.1+cu
- Socket iz nameščene Python verzije
- Pyserial 3.


- Numpy 1.21.
- Keyboard 0.13.
- CUDA 11.
- Matplotlib >= 3.2.
- Opencv-python >= 4.1.
- Pillow >= 7.1.
- PyYaml >= 5.3.
- Requests >= 2.23.
- Scipy >= 1.4.
- Tensorboard >= 2.4.
- Pandas >= 1.1.
- Seaborn >= 0.11.
- Tqdm >= 4.41.

Vozlišče na ploščici
STM ploščico uporabljamo za nadziranje načina vožnje. Uporabljamo ploščico STM32F411E-
DISCO, ki ima vgrajen kompas LSM303DLHC. Kompas uporabljamo za branje vrednosti oz
senzorja pospeškometra. Za izdelavo vozlišča kot OS uporabljamo FreeRTOS.
Uporabljena tehnologija:

- STMCubeIDE: 1.8.
    o STM32CubeMX 6.4.
    o Eclipse® 2021 - 03 and CDTTM version 10.2.
    o GNU Tools for STM32, based on _GNU Tools for Arm Embedded Processors 9-_
       _2020 - q2-update 9.3.1 20200408 (release)_
    o GNU GDB (GNU Tools for STM32 9- 2020 - q2-update) 8.1.0.20180315-git
    o AdoptOpenJDK Runtime Environment (build 11.0.11, 64-bit)
    o ST-LINK_gdbserver 6.0.0, supporting ST-LINK/V2 and STLINK-V
    o SEGGER J-Link GDB Server V7.
    o Open On-Chip Debugger 0.11.0+dev- 00438 - ga75fc63 Windows® specific build
       tools:
    o BusyBox v1.31.0.st_20200221-0903_longpath: mkdir.exe, rm.exe, echo.exe
    o make-4.2.1_st_20200221-0903_longpath: make.exe
    o Linux® specific build tools: make-4.2.1_st_20200221-0903: make
    o macOS® specific build tools: make-4.2.1_st_20200221-0903: make
- FreeRTOS 202112.
