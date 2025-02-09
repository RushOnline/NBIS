# NIST Biometric Image Software

Current NBIS Release: 5.0.0
 
## About

The NIST Biometric Image Software (NBIS) distribution is developed by the National Institute of Standards and Technology (NIST) for the Federal Bureau of Investigation (FBI) and Department of Homeland Security (DHS). This software has been determined to be outside the scope of the EAR (see Part 734.3 of the EAR for exact details) as it has been created solely by employees of the U.S. Government; it is freely distributed with no licensing requirements; and it is considered public domain. Therefore, it is permissible to distribute this software as a free download from the internet. It has been determined that the export control restriction did not apply to the NFSEG and BOZORTH3 software, due to both being outside the scope of EAR(see Part 734.3 of the EAR for exact details); they are freely distributed and considered public domain. The NBIS distribution contains C source code for use with biometrics processing and analysis. The NBIS source code is available to download from [NIST Biometric Open Source Server](http://www.nist.gov/itl/iad/ig/nigos.cfm). In addition, the [NBIS.Net project](http://bws.nist.gov/) provides a Microsoft.NET adapter for NBIS, providing an interface to the original NBIS source.

The NBIS utilities fall under eight general categories:

* A reference implementation of the [ANSI/NIST-ITL 1-2007](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=151453) (AN2K) "Data Format for the Interchange of Fingerprint, Facial, Scar Mark & Tattoo (SMT) Information" standard is included. This reference implementation contains a suite of utilities designed to read, write, edit, and manipulate files formatted according to this interchange standard. The utilities support updated and new record types introduced by this latest version of the standard (Record Types 9, 13, 14, & 15).
* Development of a new major revision of the NFIQ algorithm started in 2011 – further details on NFIQ 2.0 can be found [here](http://www.nist.gov/itl/iad/ig/development_nfiq_2.cfm). fingerprint image quality algorithm, NFIQ, which analyses a fingerprint image and assigns a quality value of 1 (highest quality) 5(lowest quality) to the image. Higher quality images produce significantly better performance with matching algorithms. The ability to retrain the NFIQ weights is provided with the utilities FING2PAT, ZNORMDAT, and ZNORMPAT.
* A neural-network based fingerprint pattern classification system called, PCASYS, automatically categorizes a fingerprint image into the class of arch, left or right loop, scar, tented arch, or whorl. This is an updated system that includes the use of a robust Multi-Layered Perceptron (MLP) neural network. It is the only known no cost system of its kind.
* A minutiae detector called, MINDTCT, automatically locates and records ridge ending and bifurcations in a fingerprint image. This system includes minutiae quality assessment based on local image conditions. The FBI's Universal Latent Workstation uses MINDTCT, and it too is the only known no cost system of its kind.
* A large collection of general-purpose image utilities (IMGTOOLS) are also included to support the processing of fingerprint images. Source code is provided for Baseline JPEG, Lossless JPEG, and the FBI's Wavelet Scalar Quantization (WSQ) encoders and decoders. (The Baseline JPEG code uses the Independent JPEG Group's compression/decompression libraries.) Utilities are also provided that support color component interleaving, colorspace conversion, and format conversion of legacy files distributed in NIST fingerprint databases.
* A fingerprint matching algorithm, BOZORTH3, which is a minutiae based fingerprint matching algorithm. It will do both one-to-one and one-to-many matching operations. It accepts minutiae generated by the MINDTCT algorithm.
* A fingerprint segmentation algorithm, NFSEG, which will segment the four-finger plain impression found on the bottom of a fingerprint card into individual fingerprint images or it can be used to remove white space from a rolled fingerprint image.
* A spectral validation/verification metric for fingerprint images , SIVV, examines an input image with respect to expression of the level-1 ridge flow in a 1-D representation of its power spectrum. Relative power and frequency location of the dominant peak indicate the presence of a fingerprint in the image, the approximate sample rate, and provide a rough measure of fingerprint quality. The algorithm is described in a technical report, NISTIR 7599, available for download at [NISTIR 7599](http://www.nist.gov/manuscript-publication-search.cfm?pub_id=903078).
 
For detail information on NBIS software, please reference to the following documents:

* [User's Guide to NIST Biometric Image Software (NBIS)](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=51097)
* [User's Guide to NIST Biometric Image Software Export Control(NBIS-EC)**](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=51096)
 
The source code has been developed using the GNU project's gcc compiler and gmake utility (www.gnu.org) , and has been tested under LINUX, Mac OS-X, and under Windows NT using the free Cygwin library and associated tools (www.cygwin.com).

### Recommendations on Biometric Quality Summarization across the Application Domain

[Quality summarization NISTIR 7422](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=51149) provides technical guidance for users of biometric quality algorithms in large-scale enterprise operations. Specifically, it recommends the computation and use of performance-related quality summaries, which, for verification, should serve as measures of the overall expected false non-match rate.

## NIST Fingerprint Image Quality

* NFIQ Compliance Testing
* [NFIQ Compliance document](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=150598) [336K]
* [Test Suite Tar file for NFIQ compliance](http://biometrics.nist.gov/cs_links/NFIS/NFIQ_Compliance_TestSuite.tar) [37.2M]
* [NISTIR 7151](http://www.nist.gov/customcf/get_pdf.cfm?pub_id=905710) [2,451K] - NIST Fingerprint Image Quality
* [Appendix A](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A.pdf) [62K] - ROC's and Data set quality distributions.
* Appendix A results for each SDK are in separate files. Each file is about 1-1.4MB in size. [A](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKA.pdf) [B](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKB.pdf) [C](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKC.pdf) [D](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKD.pdf) [E](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKE.pdf) [F](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKF.pdf) [G](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKG.pdf) [H](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKH.pdf) [I](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKI.pdf) [J](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKJ.pdf) [K](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKK.pdf) [L](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKL.pdf) [N](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKN.pdf) [VTB](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_SDKVTB.pdf) Appendix A results for the [DATASETS](http://biometrics.nist.gov/cs_links/NFIS/ir_7151A_DATASET.pdf)[104K]
* [Appendix B](http://biometrics.nist.gov/cs_links/NFIS/ir_7151B.pdf)[418K] - Trellis plots of feature vector components and performance.
 
## How to Contribute to the NBIS Project

The NIST Image Group appreciates all technical contributions to the NBIS project. If you are interested on contributing to the NBIS project, you are welcome to submit your contribution(s) electronically. To contribute, please send an email to nbis@nist.gov with the following information: Name, Organization, Contact Information and a brief description of your contribution(s).  After we have received your email, we will contact you for further information.

## Terms and conditions:

There is no guarantee that your contribution(s) will be included in the NBIS Main development branch; the integration of outside changes is at the sole discretion of the NIST Image Group. However, any changes that are integrated will fall under the same licensing terms as the original software.

## Support

Thank you for your interest in using the NBIS software. Unfortunately, we do not have the resources to provide individual support for this software, but do welcome comments for improvement. At the present time we only provide the source code for download.

## License

This software was developed at the National Institute of Standards and Technology (NIST) by employees of the Federal Government in the course of their official duties. Pursuant to [Title 17 Section 105 of the United States Code](http://www.copyright.gov/title17/92chap1.html#105), this software is not subject to copyright protection and is in the public domain. NIST assumes no responsibility whatsoever for use by other parties of its source code or open source server, and makes no guarantees, expressed or implied, about its quality, reliability, or any other characteristic.

This software has been determined to be outside the scope of the EAR (see Part 734.3 of the EAR for exact details) as it has been created solely by employees of the U.S. Government; it is freely distributed with no licensing requirements; and it is considered public domain. Therefore, it is permissible to distribute this software as a free download from the internet.

## Disclaimer

* * Specific software products identified here are used in order to perform the code management tasks at hand. However, in no case does identification of any commercial product, trade name, or vendor, imply recommendation or endorsement by the National Institute of Standards and Technology, nor does it imply that the products and equipment identified are necessarily the best available for the purpose.
* ** The "User's Guide to Non-Export Controlled" and "User's Guide to Export Controlled" is pending to combine to one document in the future release.
