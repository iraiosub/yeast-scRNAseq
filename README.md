[![Created with Ule Lab Protocol Template](https://img.shields.io/badge/created%20with-Ule%20Lab%20Protocol%20Template-blue)](https://github.com/ulelab/protocol-template)
# yeast single cell RNA-seq (yscRNA-seq)

### Status: 🟢 `[OK]`
| ***Status legend***: | 🟢 `[OK]` working | 🟡 `[?]` unconfirmed / partial | 🔴 `[X]` broken |
|---|---|---|

# About

This protocol describes yeast single-cell RNA-seq (yscRNA-seq), from yeast culture and single-cell FACS sorting through cDNA library preparation, validation, and sequencing. The source states: “Working. We use this protocol and it's working.”

**Citation:** Mariona Nadal, Saiful Islam, Wu Wei, Pablo Latorre, Michelle Nguyen, Eulàlia e Nadal, Francesc Posas, Lars M. Steinmetz (2018). *yeast single cell RNA-seq (yscRNA-seq).* protocols.io. [https://dx.doi.org/10.17504/protocols.io.t29eqh6](https://dx.doi.org/10.17504/protocols.io.t29eqh6). Protocol Integer ID: 16193.

**Date:** December 26, 2018. Created September 27, 2018; last modified December 26, 2018.

**Affiliations as listed in the source:** IRB Barcelona; Stanford Universtity, Stanford Genome Technology Center; IRB Barcelona, Universtat Pompeu Fabra; Stanford Universtity, Stanford Genome Technology Center, EMBL. The source does not clearly map the numbered affiliations to individual authors.

**License:** Open access under the Creative Commons Attribution License, which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.

**Keywords:** yeast single cell RNA-seq (yscRNA-seq), transcriptomics, single cell rna, yscrna, rna, single cell, seq.

![Yeast micrograph from the source title page](legacy/images/yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0001-04.png)

## Contents
1. [Cell growth and single-cell isolation](#1-cell-growth-and-single-cell-isolation)
2. [Cell lysis and first-strand cDNA synthesis](#2-cell-lysis-and-first-strand-cdna-synthesis)
3. [Library amplification and qPCR validation](#3-library-amplification-and-qpcr-validation)
4. [dscDNA cleanup and validation](#4-dscdna-cleanup-and-validation)
5. [Tagmentation and single-stranded cDNA preparation](#5-tagmentation-and-single-stranded-cdna-preparation)
6. [Library quantification, sizing, and sequencing](#6-library-quantification-sizing-and-sequencing)
7. [Materials](#7-materials)
8. [Migration notes](#migration-notes)

---

# 1. Cell growth and single-cell isolation

**Input / starting material:** Desired yeast strain and corresponding media.

> **Warning:** Follow all precautions normally required for RNA and single-cell work. Clean the area before starting. Use reagents dedicated to single-cell work only and label them appropriately. Use pipettes and filter tips throughout the entire protocol.

## Cell growth

- **1.** Grow the desired pre-inoculum of the desired yeast strain in its corresponding media overnight (O/N).
- To profile exponentially growing cells, the source recommends that the initial culture not grow over `OD660 CHECK: source symbol is unclear` 1.
- **2.** The next morning, dilute the cells to OD660 0.05 in the corresponding media and allow at least 2 cell divisions before sorting.

## Single-cell isolation by FACS sorting

- **3.** Prepare 96- or 384-well plates containing 5 µL absolute ethanol per well to fix cells immediately after sorting.
	- During protocol optimization, the source recommends break-away plates (EK-75118). Check plate compatibility with the facility.
	- The source identifies 5 µL as the minimum volume required for its sorting facility/plates and says to check with the facility.
- **4.** Dilute cells before sorting to OD 0.05 in 3 mL of media and vortex vigorously to separate cell clumps. Propidium iodide (PI) can be added at this step to check cell viability.
- **5.** At the FACS facility, filter cells with Cell Strainer Tubes (check with the facility which tubes they prefer) and put cells in the appropriate sorting tube for live single-cell sorting.
- **6.** Check plate alignment with the sorter. For example, sort a drop into a covered plate and check that the droplet falls inside each well.
- **7.** Sort live single yeast cells into the wells. Leave one well unsorted (the source usually uses H12) as a negative control. For a positive control, sort 100 cells into one well (the source usually uses A1).
- **8.** Cover plates with an aluminum seal if they will not be processed immediately, or use a temporary plastic lid.
- **9.** Quickly spin plates to collect cells at the bottom.
- **10.** Let ethanol evaporate in a sterile environment (sterile hood) for a maximum of 45 minutes.
- **11.** Once ethanol has completely evaporated, add 5 µL yeast cell lysis solution. The extracted source continues “of cell capturing solution and lysis”; **CHECK:** the relationship between these solution names is unclear. Spin down and freeze immediately.

> **Note:** The source reports the same results when sorting cells directly into 5 µL of cell-capturing and lysis solution. If doing so, prepare plates immediately before sorting and keep them on ice at 4 °C.

Regardless of whether cells are sorted into ethanol or cell-capturing and lysis solution, frozen plates can be stored at -80 °C for at least 6 months.

### Cell lysis solution

| Reagent | Reference | Volume (1 reaction; unit not printed in source) |
|---|---|---:|
| 1% Triton X-100 | X100-1L | 0.05 |
| UMI_Oligo dT_T31 (100 µM) | IDT | 0.2 |
| dNTP 25 mM | R0181 | 0.68 |
| 100 mM DTT | 18064014 | 0.5 |
| Zymolyase 100T (100 mg/mL) | 37340-57-1 | 0.6 |
| RNase Inhibitor (40 U/mL) | 2313A | 0.12 |
| RNase-nuclease-free H<sub>2</sub>O | 10977035 | 2.769 |
| ERCC (1:1000,0000) (5000 molecules; CHECK: dilution notation unclear) | 4456740 | 0.081 |
| **Total** |  | **5** |

---

# 2. Cell lysis and first-strand cDNA synthesis

## Lysis reaction

- **12.** Perform the following lysis cycle on freshly sorted or frozen plates, then quickly proceed to add the RT reaction for first-strand cDNA synthesis:
	- Incubate at 30 °C for at least 10 minutes.
	- Incubate at 72 °C for 3 minutes.
	- Incubate at 4 °C for 1 minute.
- The source says the cell-lysis duration has been changed up to 30 minutes.

## First-strand cDNA synthesis

- **13.** Add 5 µL reverse transcription mix (RT mix).

| Reagent | Volume (1 reaction; unit not printed in source) | Reference |
|---|---:|---|
| 5X SuperScript Stand Buffer | 2 | 18064014 |
| MgCl<sub>2</sub> (1 M) | 0.06 | AM9530G |
| Betaine (5 M) | 1.6 | 61962 |
| UMI_TSO 100 µM | 0.2 | IDT |
| SuperScript II (200 U/µL) | 0.25 | 18064014 |
| RNase inhibitor (40 U/mL) | 0.125 | 2313A |
| RNase-nuclease-free H<sub>2</sub>O | 0.765 | 10977035 |
| **Total** | **5** |  |

- **14.** Spin down the plate and perform these cycles: 42 °C for 90 minutes, 70 °C for 15 minutes, then 4 °C indefinitely. The source gives a timed duration of 1 hour 45 minutes, excluding the indefinite hold.

---

# 3. Library amplification and qPCR validation

## Library amplification

- **15.** Add 15 µL PCR mix for library amplification.

| Reagent | Volume (1 reaction; unit not printed in source) |
|---|---:|
| 10X Advantage 2 PCR buffer | 2.5 |
| dNTPs (25 mM) | 0.4 |
| UMI_PCR (10 µM) | 1.2 |
| 50X Advantage 2 polymerase mix | 0.5 |
| H<sub>2</sub>O | 10.4 |
| **Total** | **15** |

- **16.** Spin down the plate and run the following cycles. This table was converted from the extracted thermocycler image; cycle groupings are preserved.

| Program block | Temperature | Time | Repeats |
|---|---:|---:|---:|
| Initial block | 95 °C | 1 minute | 1 cycle |
| 5-cycle block | 95 °C | 20 seconds | 5 cycles |
| 5-cycle block | 58 °C | 4 minutes | 5 cycles |
| 5-cycle block | 68 °C | 6 minutes | 5 cycles |
| 9-cycle block | 95 °C | 20 seconds | 9 cycles |
| 9-cycle block | 64 °C | 30 seconds | 9 cycles |
| 9-cycle block | 68 °C | 6 minutes | 9 cycles |
| 7-cycle block | 95 °C | 30 seconds | 7 cycles |
| 7-cycle block | 64 °C | 30 seconds | 7 cycles |
| 7-cycle block | 68 °C | 7 minutes | 7 cycles |
| Final block | 72 °C | 10 minutes | 1 cycle |

> **Note:** Hold at 4 °C overnight if necessary. The source describes this as a usually safe stopping point.

## qPCR validation

- **17.** Perform a 1:20 dilution of the amplified library to check the percentage of positive libraries. Use a preferred protocol and target primers to a housekeeping gene or ERCCs. The source says this step is especially useful during protocol setup to inspect efficiency before proceeding.

| Reagent | Volume (µL) |
|---|---:|
| Sybergreen 2X | 2.5 |
| Primer mix* | 0.125 |
| H<sub>2</sub>O | 1.375 |
| DNA | 1 |

*Primer mix is a mix of forward and reverse primers (10 µM each).

qPCR cycling conditions:

| Block | Temperature and time |
|---|---|
| 1 cycle | 95 °C for 10 minutes |
| 40 cycles | 95 °C for 30 seconds; 58 °C for 30 seconds; 72 °C for 30 seconds |
| 1 cycle (melting curve) | 95 °C for 15 seconds; 60 °C for 15 seconds; 95 °C for 15 seconds |

Primer sequences for qPCR:

| Primer | Sequence |
|---|---|
| SOMN17 Fw_TDH3_probe | TCGTCAAGTTGGTCTCCTGG |
| SOMN18 Rv_TDH3_probe | GGCAACGTGTTCAACCAAGT |
| SOMN21 Fw_ADH1_probe | TGGTGCCAAGTGTTGTTCTG |
| SOMN22 Rv_ADH1_probe | GGCGAAGAAGTCCAAAGCTT |
| SOMN310 Fw_5_ERCC_00130 | CGGAAAAGTACTGACCAGCG |
| SOMN311 Rv_5_ERCC_00130 | TGCCAATGACTTCAGCTGAC |

The source says a good plate will have around 70% positive wells; around 50% should be OK. Rearrange positive cells into a new plate to proceed to tagmentation.

---

# 4. dscDNA cleanup and validation

- **18.** Before purification, equilibrate Ampure XP beads at room temperature for 15 minutes, then vortex well for several seconds. Add 15 µL Ampure XP beads (1:0.6 ratio) to each sample; each tube may have a slightly different volume due to evaporation. Do not increase the bead volume above a 1:1 ratio. The source says that using less than the standard amount of beads minimizes primer-dimer carryover.
- **19.** Mix by pipetting up and down 10 times or until homogeneous. Transfer solutions to a 96-well plate with a compatible magnet stand.
- **20.** Incubate for 10 minutes at room temperature to let DNA bind to the beads.
- **21.** Place the plate on the magnetic stand for 5 minutes or until the solution is clear and the beads have collected.
- **22.** With samples on the magnet, carefully remove the liquid without disturbing the beads.
- **23.** Wash beads with 200 µL of 80% (vol/vol) ethanol. Incubate for 30 seconds, then remove the ethanol. The ethanol solution must be freshly prepared each time because it absorbs moisture from the environment, changing its final concentration. The source says to repeat the ethanol wash.
- **24.** Repeat the ethanol wash one more time.
- **25.** Remove all traces of ethanol and dry the beads at room temperature for 5 minutes or until a small crack appears on the bead surface. Avoid overdrying because it makes resuspension in the designated buffer more difficult. As a precaution, cover the plate or protect it from contamination and air flows that could disperse beads between adjacent wells and cause cross-contamination.
- **26.** When the beads are dry, elute dscDNA libraries with 16.5 µL elution buffer (EB buffer, Qiagen; 19086).
- **27.** Remove the plate from the magnet and mix vigorously by pipetting up and down 3 times to resuspend the beads off the magnet.
- **28.** Place the plate on the magnetic stand for 2 minutes or until the solution appears clear and beads have accumulated in a corner of the well.
- **29.** Recover “15 mL” of supernatant (SPN) from each well and transfer it to a new plate. Label correctly because this plate will be stored.

> **Safe stopping point:** dscDNA libraries can be stored at -20 °C before proceeding to tagmentation.

## dscDNA library concentration and size validation

- **30.** Run 1 µL of several purified dscDNA libraries to check size distribution and estimate concentration using a High Sensitivity DNA ChIP (2100 Bioanalyzer). qPCR validation using a housekeeping gene is valuable for guiding well selection. Always run the negative control.

![Expected dscDNA library Bioanalyzer results from the source](legacy/images/yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0010-01.png)

---

# 5. Tagmentation and single-stranded cDNA preparation

## Adaptor annealing for tagmentation

- **31.** To load Tn5 with cell-specific adaptors, anneal the adaptors as double-stranded DNA cell-specific adaptors. In a 96-well plate, mix UMI-TN5-U (100 µM) and UMI-TN5_1 (source concentration is incomplete; see `CHECK:` items) in 1X TE to a final concentration of 50 µM each, a 1:1 dilution.
- Primer-annealing thermocycler: 95 °C for 3 minutes, then gradually cool to room temperature at 0.5 °C/second.
- The plate can be stored at -20 °C for several months and used for several rounds of Tn5 loading.

## Tn5 loading with cell-specific adaptors

- **32.** Prepare the mix below. Aliquot 8.75 µL of the mix, excluding adapters, into a new 96-well plate. Then add 1.25 µL of each adaptor to each well.

| Reagent | Volume | Observations |
|---|---:|---|
| 50 µM adapter (96 different) | 1.25 µL | Add individually to each well later. |
| 80% glycerol | 6.25 µL |  |
| 50 µM Tn5 transposase | 1.25 µL | Hennig, Bianca P., et al. “Large-Scale Low-Cost NGS Library Preparation Using a Robust Tn5 Purification and Tagmentation Protocol.” *G3: Genes, Genomes, Genetics* (2017): g3-300257. |
| Nuclease-free water | 1.25 µL |  |
| **Total volume** | **10 µL** |  |

- **33.** Incubate at 37 °C for 1 hour and freeze at -20 °C if not using right away.

> **Note:** The source says the Tn5-loaded plate can be stored safely for 1-2 weeks at -20 °C. Leaving the loaded plate on ice at 4 °C will significantly reduce Tn5 activity and result in inefficient tagmentation.

## Tagmentation

- **34.** Prepare the following mix:

| Reagent | Volume per well |
|---|---:|
| Harvested DNA | 6 µL |
| Nuclease-free water | 8 µL |
| 2X TAPS buffer | 2 µL |
| 100% DMF | 2 µL |
| 10X Transposome | 2.0 µL |
| **Total volume** | **20 µL** |

- **35.** Incubate at 55 °C for 5 minutes, then at 85 °C for 3 minutes to inactivate Tn5, and cool to 4 °C.

> **Note:** Tagmentation time can vary depending on the Tn5 purification batch.

## 5' capture through Streptavidin beads

- **36.** Make a 1:20 dilution of MyOne Streptavidin for the total number of samples (1 µL of beads per sample; for example, 20 µL beads for 20 samples).

2XBWT buffer:

| Component | Concentration |
|---|---:|
| Tris-HCl, pH 7.5 | 10 mM |
| EDTA | 1 mM |
| NaCl | 2 M |
| Tween-20 | 0.02% |

- **37.** Wash MyOne beads twice with 2XBWT buffer and resuspend in 20 times the original bead volume of 2XBWT. For example, resuspend 20 µL beads (for 20 samples) in 400 µL 2XBWT.
- **38.** Add 20 µL beads to each well and incubate at room temperature for 5 minutes.
- **39.** Pool all samples into one 1.5- or 2-mL collecting tube.
- **40.** Place the collecting tube in a magnetic rack and allow enough time for the solution to become completely clear.
- **41.** Wash beads once with 100 µL TNT buffer.

TNT buffer: 20 mM Tris, pH 7.5; 50 mM NaCl; 0.02% Tween.

- **42.** Wash beads once with 100 µL Qiaquick PB; discard the supernatant (SPN).
- **43.** Wash beads 3 times with 100 µL TNT buffer; discard the SPN again.

## Removing 3' end fragments

- **44.** Resuspend beads in the following mix:

| Reagent | Volume |
|---|---:|
| CutSmart buffer | 10 µL |
| PvuI-HF enzyme (20 U/µL) | 2 µL |
| Nuclease-free water | 88 µL |
| **Total volume** | **100 µL** |

- **45.** Incubate at 37 °C for 1 hour, mixing at intervals to avoid bead precipitation: 2 minutes without mixing, then 30 seconds mixing at 1000 rpm.
- **46.** Wash beads 3 times with 100 µL TNT.

## Eluting single-stranded cDNA library

- **47.** Resuspend beads in 30 µL nuclease-free water.
- **48.** Incubate for 10 minutes at 70 °C with mixing at 850 rpm.
- **49.** Immediately bind beads to the magnet and collect the supernatant.

## sscDNA cleanup

- **50.** Add 54 µL room-temperature Ampure XP beads to 30 µL sscDNA library.
- **51.** Incubate for 10 minutes at room temperature.
- **52.** Bind beads to the magnet for 1 minute and discard the supernatant, or wait until the solution is completely clear.
- **53.** Wash once with 200 µL fresh 80% ethanol for 20-30 seconds. Keep beads bound to the magnet throughout.
- **54.** Dry beads for up to 2 minutes.
- **55.** Resuspend in 30 µL Qiagen EB buffer and incubate for 5 minutes at room temperature.
- **56.** Bind beads for 1 minute and transfer the supernatant (SPN) to a new tube.

---

# 6. Library quantification, sizing, and sequencing

## Library concentration

- **57.** To quantify library concentration, set up a KAPA quantification reaction with 1:100 and 1:1000 dilutions of the eluted cDNA library.

| Reagent | Volume (1 reaction) |
|---|---:|
| KAPA SYBR FAST qPCR Master Mix containing Primer Premix | 12 µL |
| PCR-grade water | 4 µ (unit incomplete in source) |
| Diluted library DNA or DNA Standard | 4 µL |
| **Total** | **20 µL** |

The source says this kit can be replaced by a preferred quantification method or by qPCR using P5-P7 primer pairs with known standards (PhiX strongly recommended) and Sybergreen 2X mastermix.

- **58.** qPCR cycling conditions for KAPA and homemade Sybergreen:

| Block | Temperature | Time | Repeats |
|---|---:|---:|---:|
| Initial | 95 °C | 5 minutes | 1 cycle |
| Amplification | 95 °C | 30 seconds | 30 cycles |
| Amplification | 60 °C | 45 seconds | 30 cycles |
| Hold | 4 °C | Hold |  |

- **59.** Use qPCR to calculate library quantification with the template provided by KAPA Biosystems or the instructions provided by the manufacturer. The source reports similar results with KAPA, NEB, and homemade systems.

## Library size

- **60.** Set up a separate PCR to run a Bioanalyzer and determine the final size distribution. Prepare the following mix; the table combines the extracted table spanning source pages 16-17.

| Reagent | Volume |
|---|---:|
| KAPA SYBR Q-PCR Mastermix ABI Prism | 10 µL |
| Primers mix (10X) | 2 µL |
| Water | 6 µL |
| DNA without dilution | 2 µL |
| **Total volume** | **20 µL** |

- **61.** Run the same PCR as in step 58 but for 11 cycles.
- **62.** Run 1 µL into a High Sensitivity DNA CHIP to obtain an average library size based on the Bioanalyzer profile.

![Expected final library Bioanalyzer results from the source](legacy/images/yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0017-03.png)

## Sequencing

- **63.** Sequence the library on the HiSeq 2000 High Output using C1-P1-PCR-2 as the Read 1 primer and UMI-TN5-U as the Index read primer.
- **64.** To run libraries on the HiSeq Rapid Run, use LNA primers. The source says, “Spike in at primer at 0.5 µM.” Put Index 1 primer into HP8 (position 17) in the HiSeq, and Read 1 primer into HP9 (position 16) in the HiSeq. Double-check this information with the sequencing kit/instrument.

	- UMI_PCR_read1: `+GAATGA+TACGGCG+ACCA +CCGA+T` - custom 250 nmole DNA oligo, HPLC purification.
	- Index1: `CTGT+CT+CTT+ATA+CA +CA+TCTGA+CG+C` - custom 250 nmole DNA oligo, HPLC purification.

> **Note:** For a High Output run, custom primers are needed as well, but without LNA.

- **65.** Load around 8-14 pmol of each library per lane. Libraries are single-stranded DNA, so denaturing is not required.

---

# 7. Materials

## 7.1 Buffers

- 1X TE buffer
- 2XBWT buffer (composition in section 5)
- TNT buffer (composition in section 5)
- CutSmart buffer
- Qiagen EB buffer (elution buffer; 19086)
- Qiaquick PB
- Fresh 80% ethanol

## 7.2 Reagents

- Absolute ethanol
- Ampure XP beads
- Betaine (5 M)
- dNTPs (25 mM for cell lysis; 25 mM for library amplification)
- DTT (100 mM)
- ERCC (1:1000,0000; 5000 molecules)
- KAPA SYBR FAST qPCR Master Mix containing Primer Premix
- MgCl<sub>2</sub> (1 M)
- MyOne Streptavidin beads
- Nuclease-free water
- PvuI-HF enzyme (20 U/µL)
- RNase inhibitor (40 U/mL)
- SuperScript II (200 U/µL)
- Sybergreen 2X mastermix
- TAPS buffer (2X)
- Tn5 transposase (50 µM)
- Triton X-100 (1%)
- UMI_Oligo dT_T31 (100 µM)
- UMI_TSO (100 µM)
- UMI_PCR (10 µM)
- Zymolyase 100T (100 mg/mL)
- 80% glycerol

## 7.3 Equipment and consumables

- 96- or 384-well plates; break-away plates recommended during optimization (EK-75118)
- Aluminum plate seal or temporary plastic lid
- Cell Strainer Tubes
- FACS sorter and compatible sorting tubes
- Compatible magnetic stand and magnetic rack
- 1.5- or 2-mL collecting tube
- High Sensitivity DNA ChIP / High Sensitivity DNA CHIP and 2100 Bioanalyzer
- HiSeq 2000
- Pipettes and filter tips

---

# Migration notes

- Source files: `legacy/source.md`, `legacy/source.txt`, `legacy/source-metadata.yml`, and the PDF `legacy/yeast-single-cell-rna-seq-yscrna-seq-t29eqh6 (1).pdf`.
- Source metadata imported: `source_type: pdf`. Other `source-metadata.yml` fields are blank or placeholders.
- Template version: 1.1.0 (`docs/template-metadata.yml`).
- Migration date: 2026-10-12.
- Formatting normalized: headings and list structure; time units expanded; unit spacing/capitalization and temperature spacing standardized; common chemical formulas use HTML subscripts; notes and warnings use blockquotes. Source reagent names, steps, order, quantities, conditions, and primer sequences were otherwise retained.
- **CHECK:** The authors’ numbered affiliations are not clearly mapped in the extracted source; affiliation wording was kept as extracted. The category text “Yeast Protocols, Tools, a…” is truncated.
- Direct comparison against the original PDF was not possible in this environment because no PDF reader, renderer, or PDF Python package is installed. Source Markdown, source text, and all extracted images were reviewed. Check the flagged items below against the original PDF before using the protocol.
- Image-based tables converted to Markdown: `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0007-00.png` (library-amplification thermocycler program), `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0012-02.png` (tagmentation mix), and `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0016-08.png` plus `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0017-00.png` (library-size PCR mix and total row).
- Images retained: `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0001-04.png` (yeast micrograph; source context is not explicit), `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0010-01.png` (dscDNA expected result), and `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0017-03.png` (final library expected result).
- Images omitted as non-protocol page/access content: `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0001-09.png` (profile icon), `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0001-15.png` (Open Access mark), and `yeast-single-cell-rna-seq-yscrna-seq-t29eqh6_-1-.pdf-0001-16.png` (QR code; the DOI is also present as text). The source's account-creation text was also omitted as platform chrome.
- No other extracted image was left unclassified. No substantive protocol content was intentionally placed outside the mapped steps; `## Unplaced content` is empty.

## Unplaced content
None.

## CHECK items
- **CHECK:** The extracted symbol in the exponential-growth threshold “OD660 ... 1” is not legible as a comparison operator; it is retained as uncertain in section 1.
- **CHECK:** Step 29 gives an unusually large “15 mL” SPN volume per well. The quantity may be corrupted, but it is preserved without guessing.
- **CHECK:** Step 31 gives UMI-TN5_1 as “(µM)” without a concentration, despite the stated 50 µM final concentration and 1:1 dilution.
- **CHECK:** Step 57 lists PCR-grade water as “4 µ” without a complete unit.
- **CHECK:** Verify HiSeq Rapid Run primer placement and the 0.5 µM spike-in instructions against the sequencing kit/instrument; the source itself says to double-check.
- **CHECK:** The source title-page micrograph is retained because it may be protocol-related, but its role is not stated.
