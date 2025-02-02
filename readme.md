# 3D NIfTI to DICOM Converter

This repository provides a Python function that converts 3D NIfTI medical images into a series of DICOM slices. The code is intentionally kept straightforward and minimal so you can easily adapt it to your own needs and pipelines.

## Table of Contents

1. [Features](#features)  
2. [Requirements](#requirements)  
3. [Example](#example)  
4. [License](#license)   

---

## Features

- **NIfTI to DICOM Conversion**: Converts 3D volume data from NIfTI (`.nii`, `.nii.gz`) format to standard DICOM files.
- **Lightweight and Adaptable**: The code is kept simple for easy customization—perfect for research or clinical prototyping.
- **GPL License**: Distributed under the [GNU General Public License (GPL)](./LICENSE), ensuring the freedom to modify and redistribute.

---

## Requirements

- [Python 3.7+](https://www.python.org/)
- [nibabel](https://pypi.org/project/nibabel/) (for loading NIfTI images)
- [pydicom 3.0+](https://pypi.org/project/pydicom/) (for creating and saving DICOM files)
- [numpy](https://pypi.org/project/numpy/) (for numerical operations)

---

## Example

Below is a minimal example demonstrating how to convert a NIfTI file named `input_image.nii.gz` into multiple DICOM slices in a folder called `dicom_output`:

```python
import nibabel as nib
from nifti_to_dicom import nifti_3d_to_dicom

# Load NIfTI
nifti_img = nib.load("input_image.nii.gz")

# Convert and save to DICOM
nifti_3d_to_dicom(
    nifti_img=nifti_img,
    output_folder="dicom_output",
    PatientName="JohnDoe",
    PatientID="12345678",
    Modality="CT",
    SeriesDescription="Simple CT Example",
    StudyDescription="Demo Study",
    SeriesNumber=1
)
```

---

## License

This project is licensed under the GNU General Public License 3.0 (GPL) by  
**Dr. med. Hinrich Winther, Machine Learning Work Group, Institute of Diagnostic and Interventional Radiology, Hannover Medical School**.

You are free to copy, modify, and distribute this software with the same license.
