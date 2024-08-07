---
title: Meeting 001
date:
  - 17-07-2024
time: 13:00 BST
author: Luca Trautmann
tags:
  - None
series: None
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-07-18
---
# Meeting 001
## Noteworthy
- Discussion revolved around the paper [[@liu2021]] on a novel low-field MRI scanner that does not require external radio-frequency shielding. Instead a CNN was used to calculate residual noise maps that mapped the radio-frequency noise in the total signal. 
	- The approach is akin to ANC in headphones. 
	- Requires a calibration phase for each room to assess the background RF and might therefore not be the ideal solution
		- _Issues have been raised with proprietary technology used in a different company low-field scanner, but that should not be an issue for experimental research_
	- The CNN architecture needs to be evaluated further. Some aspects in the method section do not seem to be well thought out. 
- Other issues that have been raised are the increases in sensor and magnet temperature in the machine that could be resulting from the patient being placed in the machine for extended periods of time or external factors such as the sun
	- Requires some experimentation to determine whether this leads to issues with the SNR or other degradations
