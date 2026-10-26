# SinFUND and SinOCR Datasets

This repository contains two datasets, **SinFUND** and **SinOCR**, aimed at enhancing handwritten and printed Optical Character Recognition (OCR) and form understanding for the Sinhala language. 

Users of the **SinFUND** and **SinOCR** datasets are kindly requested to cite the following preprint:

Kavishka Gunathilaka, Danusha Hewagama, Supul Pushpakumara, et al. *SinFUND and SinOCR: Benchmarks for Sinhala Handwritten OCR and Template-Free Form Understanding*. Preprint (Version 1), Research Square, 03 September 2025.  
Available at: [https://doi.org/10.21203/rs.3.rs-6976719/v1](https://doi.org/10.21203/rs.3.rs-6976719/v1)

## SinFUND Dataset

The **SinFUND** dataset is a collection of scanned images of handwritten Sinhala forms, designed to support the development of form understanding and information extraction systems. It containes a diverse range of Sinhal forms.

## SinOCR Dataset

The **SinOCR** dataset is a collection of printed and handwritten Sinhala text images, created to facilitate the training and evaluation of OCR systems for the Sinhala language. It covers a wide variety of text styles and fonts.

## Access to the Datasets

You may access the SinFUND and SinOCR datasets through the following link.
[Access SinFUND and SinOCR Datasets](https://drive.google.com/drive/folders/1Czf8dQkEzWXBBcmVbBNa2OaMwdBBvBsx?usp=sharing)

## Licence

The SinFUND and SinOCR datasets are released under the Creative Commons Attribution 4.0 International licence (CC BY 4.0); see [LICENSE](LICENSE). You may share and adapt the data for any purpose, provided that you cite the paper above. All personal details written on the SinFUND forms are fictitious.

## Fixed splits

- **SinFUND:** `training_data` (`sin_train_0` to `sin_train_79`, 80 forms) and `testing_data` (`sin_val_0` to `sin_val_19`, 20 forms). Following the XFUND naming convention, the test files carry the suffix `val`; there is no separate validation split.
- **SinOCR handwritten:** `train/data.csv` (908 lines) and `test/data.csv` (227 lines).
- **SinOCR printed:** `train/gt.csv` (90,000 lines) and `test/gt.csv` (10,000 lines).

## Source of the handwritten SinOCR lines

[`sinocr_handwritten_provenance.csv`](sinocr_handwritten_provenance.csv) states, for every handwritten SinOCR image, whether it was cropped from a SinFUND form (and from which form and answer box) or collected through the web application.

132 SinOCR training lines are crops from SinFUND **test** forms. If you evaluate an OCR model trained on SinOCR on the SinFUND test split (for example, in an end-to-end OCR, entity-recognition and relation-extraction pipeline), first remove the rows with `sinocr_split = train` and `origin = sinfund_test` from the OCR training data.
