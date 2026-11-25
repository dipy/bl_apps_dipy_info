<h1 align="center">DWI Info</h1>

<p align="center">
  Reports basic information about a DWI dataset (image header, b-values/shells and b-vector checks) with DIPY dipy_info 1.1.1, as text files.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/bl.app.63"><img src="https://img.shields.io/badge/Brainlife-bl.app.63-blue.svg" alt="Run on brainlife.io"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-see_LICENSE-lightgrey.svg" alt="License"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Reports basic information about a DWI dataset (image header, b-values/shells and b-vector checks) with DIPY dipy_info 1.1.1, as text files.**

Runs dipy_info three times: on the DWI image, on the bvecs (checking unit norm within bvecs_tol) and on the bvals (counting b0 volumes below b0_threshold and grouping shells within bshell_thr). Use it as a quick sanity check of DWI data before processing; it does not modify the data.

| | |
|---|---|
| **Inputs** | `neuro/dwi` |
| **Outputs** | `raw` |
| **Container** | `brainlife/dipy:1.1.1` |
| **Resources** | 8 CPUs |
| **Run it** | [doi.org/10.25663/bl.app.63](https://doi.org/10.25663/bl.app.63) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `dwi` | `neuro/dwi` | yes | Diffusion-weighted image with its bvals and bvecs. |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `output` | `raw` | Text reports dwi_info.txt, bvecs_info.txt and bvals_info.txt. |

<details>
<summary><b>Parameters</b> (3)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `bvecs_tol` | number | `0.01` | Threshold used to check that norm(bvec) = 1 +/- bvecs_tol b-vectors are unit vectors (default 0.01). |
| `b0_threshold` | number | `50` | b-value at or below which a volume is treated as b0 when summarising the bvals. |
| `bshell_thr` | number | `100` | The threshold for distinguishing b-values in different shells (default 100). |

</details>

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/bl.app.63](https://doi.org/10.25663/bl.app.63), choose `neuro/dwi` from your project, set the parameters and press **Execute**. The results are saved to your project as `raw`.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) (the App runs in `brainlife/dipy:1.1.1`), [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "bvals": "/path/to/dwi/bvals",
       "dwi": "/path/to/dwi/dwi",
       "bvecs": "/path/to/dwi/bvecs",
       "bvecs_tol": 0.01,
       "b0_threshold": 50,
       "bshell_thr": 100
   }
   ```

3. Run `./main`.

## DIPY

- This is a Brainlife wrapper App stemming from the [`dipy_info`](https://dipy.org/documentation/latest/reference_cmd/dipy_info/) workflow.
- This single wrapper is exposed through an apps registered on [Brainlife.io](https://brainlife.io).
- More information about DIPY : [https://dipy.org/](https://dipy.org/).
- More information about the command line `dipy_info`: [Command line Reference](https://dipy.org/documentation/latest/reference_cmd/dipy_info/).

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- DWI Info. brainlife.io App. [doi:10.25663/bl.app.63](https://doi.org/10.25663/bl.app.63)
- Garyfallidis E et al. Dipy, a library for the analysis of diffusion MRI data. Frontiers in Neuroinformatics 8:8 (2014). [doi:10.3389/fninf.2014.00008](https://doi.org/10.3389/fninf.2014.00008)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

- Serge Koudoro
- Javier Ricardo Guaje Guerra

**Contributors**

- Soichi Hayashi

## Funding

[![Wellcome-226486/Z/22/Z](https://img.shields.io/badge/Wellcome-226486%2FZ%2F22%2FZ-purple.svg)](https://wellcome.org/)
[![NIH-NINDS-U24NS140384](https://img.shields.io/badge/NIH_NINDS-U24NS140384-green.svg)](https://reporter.nih.gov/project-details/11261037)
[![NIH-NINDS-UM1NS132207](https://img.shields.io/badge/NIH_NINDS-UM1NS132207-green.svg)](https://reporter.nih.gov/project-details/11411328)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://reporter.nih.gov/project-details/10262925)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://reporter.nih.gov/project-details/10428625)
[![NIH-NIMH-R01MH126699](https://img.shields.io/badge/NIH_NIMH-R01MH126699-green.svg)](https://reporter.nih.gov/project-details/10460628)
[![NIH-NIDCD-R01DC020088](https://img.shields.io/badge/NIH_NIDCD-R01DC020088-green.svg)](https://reporter.nih.gov/project-details/11140284)
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-2203524](https://img.shields.io/badge/NSF_BCS-2203524-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2203524)
[![NSF-IIS-1636893](https://img.shields.io/badge/NSF_IIS-1636893-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-OAC-2148729](https://img.shields.io/badge/NSF_OAC-2148729-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148729)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NSF-IIS-2148700](https://img.shields.io/badge/NSF_IIS-2148700-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148700)
[![NSF-OAC-1916518](https://img.shields.io/badge/NSF_OAC-1916518-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1916518)

<sub>brainlife.io, which runs this App, is publicly funded by Wellcome, the U.S. National Institutes of Health and the U.S. National Science Foundation; acknowledging that support helps keep it running.</sub>

## License

See [LICENSE](LICENSE).
