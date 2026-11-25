[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.63-blue.svg)](https://doi.org/10.25663/bl.app.63)

# Dipy Info

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Reports basic information about a DWI dataset (image header, b-values/shells and b-vector checks) with DIPY dipy_info 1.1.1, as text files.**

Runs dipy_info three times: on the DWI image, on the bvecs (checking unit norm within bvecs_tol) and on the bvals (counting b0 volumes below b0_threshold and grouping shells within bshell_thr). Use it as a quick sanity check of DWI data before processing; it does not modify the data.

| | |
|---|---|
| 📥 **Inputs** | `neuro/dwi` |
| 📤 **Outputs** | `raw` |
| 🐳 **Container** | `brainlife/dipy:1.1.1` |
| ⚙️ **Resources** | 8 CPUs |
| 🔗 **Run it** | [doi.org/10.25663/bl.app.63](https://doi.org/10.25663/bl.app.63) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `dwi` | `neuro/dwi` | yes | Diffusion-weighted image with its bvals and bvecs. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `output` | `raw` | Text reports dwi_info.txt, bvecs_info.txt and bvals_info.txt. |

<details>
<summary><b>⚙️ Parameters</b> (3)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `bvecs_tol` | number | `0.01` | Threshold used to check that norm(bvec) = 1 +/- bvecs_tol b-vectors are unit vectors (default 0.01). |
| `b0_threshold` | number | `50` | b-value at or below which a volume is treated as b0 when summarising the bvals. |
| `bshell_thr` | number | `100` | The threshold for distinguishing b-values in different shells (default 100). |

</details>

📚 **References used by this App:**
- Garyfallidis E et al. Dipy, a library for the analysis of diffusion MRI data. Frontiers in Neuroinformatics 8:8 (2014). [doi:10.3389/fninf.2014.00008](https://doi.org/10.3389/fninf.2014.00008)

<!-- brainlife-app:end -->

The App provides information about your the diffusion-weighted magnetic resonance imaging data.

### Authors
- [Serge Koudoro](skoudoro@iu.edu)
- [Javier Ricardo Guaje Guerra](jrguajeg@iu.edu)

### Contributors
- [Soichi Hayashi](soichih@gmail.com)

### Funding Acknowledgement
brainlife.io is publicly funded and for the sustainability of the project it is helpful to Acknowledge the use of the platform. We kindly ask that you acknowledge the funding below in your code and publications. Copy and past the following lines into your repository when using this code.

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://grantome.com/grant/NIH/R01-EB029272-01)

### Citations
We ask that you the following articles when publishing papers that used data, code or other resources created by the brainlife.io community.

1. Garyfallidis, E., Brett, M., Amirbekian, B., Rokem, A., van der Walt, S., Descoteaux, M., Nimmo-Smith, I., & Dipy Contributors (2014). Dipy, a library for the analysis of diffusion MRI data. Frontiers in neuroinformatics, 8, 8. [https://doi.org/10.3389/fninf.2014.00008](https://doi.org/10.3389/fninf.2014.00008)

2. Avesani, P., McPherson, B., Hayashi, S. et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6, 69 (2019). [https://doi.org/10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Running the App

#### 1. On Brainlife.io

You can see a list of [Dipy Apps currently regsitered on Brainlife](https://brainlife.io/apps#dipy). Find the App that you'd like to run and click "Execute" tab to specify dataset that you'd like to run the App on.

#### 2. On  your machine (Running Locally)

To run this command, you can simply type:

`singularity exec -e docker://brainlife/dipy:1.1.1 dipy_info [your_args]`

To see the documentation of all arguments, [go to the following page](https://dipy.org/documentation/1.1.1./reference_cmd/dipy_info/)

## Input

To see the documentation of all the arguments, follow this [link](https://dipy.org/documentation/1.1.1./reference_cmd/dipy_info/).

## Output

All output files will be generated according to the passed arguments, as explained [here](https://dipy.org/documentation/1.1.1./reference_cmd/dipy_info/).

### Dependencies

This app runs on [singularity](https://www.sylabs.io/singularity/).

### DIPY
- This is a Brainlife wrapper App stemming from the [`dipy_info`](https://dipy.org/documentation/latest/reference_cmd/dipy_info/) workflow.
- This single wrapper is exposed through an apps registered on [Brainlife.io](https://brainlife.io).
- More information about DIPY : [https://dipy.org/](https://dipy.org/).
- More information about the command line `dipy_info`: [Command line Reference](https://dipy.org/documentation/latest/reference_cmd/dipy_info/).
