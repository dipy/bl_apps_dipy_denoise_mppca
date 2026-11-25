[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.326-blue.svg)](https://doi.org/10.25663/brainlife.app.326)

# Dipy Denoise Diffusion MRI using MP-PCA

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Denoises DWI with Marcenko-Pastur PCA (MP-PCA) using the DIPY 1.1.1 dipy_denoise_mppca workflow and outputs the denoised DWI with its bvals and bvecs.**

Wraps DIPY's dipy_denoise_mppca, which removes thermal noise from diffusion-weighted data by local PCA with a Marcenko-Pastur threshold over patches of a given radius. Use it as an early DWI preprocessing step, before motion and distortion correction. The bvals and bvecs are copied unchanged to the output.

| | |
|---|---|
| 📥 **Inputs** | `neuro/dwi` |
| 📤 **Outputs** | `neuro/dwi` |
| 🐳 **Container** | `brainlife/dipy:1.1.1` |
| ⚙️ **Resources** | 12 CPUs |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.326](https://doi.org/10.25663/brainlife.app.326) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `dwi` | `neuro/dwi` | yes | 4D diffusion-weighted image with bvals and bvecs. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `output` | `neuro/dwi` | MP-PCA denoised DWI (dwi.nii.gz) with the original bvals and bvecs. |

<details>
<summary><b>⚙️ Parameters</b> (2)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `patch_radius` | number | `2` | The radius of the local patch to be taken around each voxel (in voxels) |
| `pca_method` | string | `eig` | Use either eigenvalue decomposition ('eig') or singular value decomposition ('svd') for principal component analysis. The default method is 'eig' which is faster. However, occasionally 'svd' might be more accurate. |

</details>

📚 **References used by this App:**
- Garyfallidis E. et al. Dipy, a library for the analysis of diffusion MRI data. Frontiers in Neuroinformatics 8, 8 (2014).
- Avesani P. et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6, 69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

<!-- brainlife-app:end -->

The App uses the Marcenko-Pastur Principal Component Analysis (MP-PCA) method to denoise diffusion-weighted magnetic resonance imaging data.

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

### On Brainlife.io

You can see a list of [DIPY Apps currently registered on Brainlife](https://brainlife.io/apps#dipy). Find the App that you'd like to run and click "Execute".

### Running Locally (on  your machine)

To run this command, you can simply type:

```bash
singularity exec -e docker://brainlife/dipy:1.1.1 dipy_denoise_mppca [your_args]
```

## Input

To see the documentation of all the arguments, follow this [link](https://dipy.org/documentation/1.1.1./reference_cmd/dipy_denoise_mppca/).

## Output

All output files will be generated according to the passed arguments, as explained [here](https://dipy.org/documentation/1.1.1./reference_cmd/dipy_denoise_mppca/).

### Dependencies

This app runs on [singularity](https://www.sylabs.io/singularity/).

### DIPY
- This is a Brainlife wrapper App stemming from the [`dipy_denoise_mppca`](https://dipy.org/documentation/latest/reference_cmd/dipy_denoise_mppca/)  workflow.
- This single wrapper is exposed through an apps registered on [Brainlife.io](https://brainlife.io).
- More information about DIPY : [https://dipy.org/](https://dipy.org/).
- More information about the command line `dipy_denoise_mppca`: [Command line Reference](https://dipy.org/documentation/latest/reference_cmd/dipy_denoise_mppca/).
