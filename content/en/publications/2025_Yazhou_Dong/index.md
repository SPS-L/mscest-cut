+++
title = "Development of a low-cost Micro-PMU (µPMU)"
date = "2025-06-01"
authors = ["Yazhou Dong"]
tags = [micro-PMU, "phasor measurement unit", "low-cost instrumentation", "power grid monitoring"]
publication_types = ["thesis"]
publication = "_Cyprus University of Technology_"
publication_short = ""
abstract = ""
summary = ""
featured = false
projects = []
slides = ""
url_code = ""
url_dataset = ""
url_poster = ""
url_slides = ""
url_source = ""
url_video = ""
math = true
highlight = true
[image]
image = ""
caption = ""
+++

## Overview

This master’s thesis, titled **Development of a low-cost Micro-PMU (µPMU)**, presents the design, implementation, and evaluation of a cost-effective micro-phasor measurement unit (µPMU) for power grid applications. Authored by Yazhou Dong and submitted to the Cyprus University of Technology in December 2024, the work addresses the growing need for affordable, high-precision monitoring solutions in modern electrical distribution networks. The thesis is supervised by Prof. Petros Aristidou and is situated within the Department of Electrical Engineering and Computer Engineering and Informatics.

The document opens with an introduction to the challenges and opportunities in power system monitoring, emphasizing the limitations of traditional Supervisory Control and Data Acquisition (SCADA) systems and the advantages of PMUs. The literature review provides a comparative analysis of SCADA, conventional PMUs, and emerging µPMU technologies, highlighting recent advances and persisting gaps in low-cost, high-accuracy measurement solutions.

## Key Contributions

- **Comprehensive Comparison:** The thesis systematically compares SCADA, PMU, and µPMU technologies in terms of functionality, cost, and accuracy, providing a clear rationale for the development of low-cost µPMUs.

- **Hardware and Software Design:** Detailed methodologies are presented for both hardware and software components. The hardware section covers the selection and integration of control units, signal processing circuits, data acquisition modules, and wireless communication systems. The software section addresses system architecture, GPS data parsing, signal acquisition algorithms, and wireless data transmission.

- **Algorithm Implementation:** The thesis implements and tests advanced phasor measurement algorithms, including the Interpolated Discrete Fourier Transform (IPDFT), to enhance measurement accuracy while maintaining low system cost.

- **Experimental Validation:** Extensive testing is conducted to evaluate the performance of the developed µPMU. Results include hardware function tests, synchronous data acquisition, voltage and current measurement accuracy, and error analysis. Comparative tables summarize the performance against existing solutions.

- **Cloud Integration:** The work explores cloud-based data management, enabling scalable and remote access to measurement data, which is essential for modern smart grid applications.

## Impact and Relevance

The thesis makes significant contributions to the field of power system monitoring by demonstrating that high-precision phasor measurement can be achieved with low-cost hardware and open-source software. This democratizes access to advanced grid monitoring, particularly for smaller utilities and developing regions where budget constraints are critical.

By providing a detailed blueprint for both hardware and software, the work serves as a valuable reference for researchers and practitioners aiming to deploy µPMUs in real-world distribution networks. The inclusion of cloud integration further aligns the solution with current trends in digitalization and smart grid evolution.

The research addresses key gaps in the literature by offering a validated, scalable, and affordable alternative to traditional PMUs. Its findings have the potential to accelerate the adoption of µPMUs, improve grid reliability, and support the integration of renewable energy sources through enhanced situational awareness and data-driven decision-making.