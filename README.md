# LIFE-Series-III  
  
Cloud- and scattering-free spectra of an Earth-twin used as input for the retrievals in LIFE III   (Konrad et al. 2022; A&A 664, A23).  
  
All spectra were generated using petitRADTRANS assuming the parameter values listed in  
the "Input" column of Table 3 in the publication. The used line-lists are provided in  
Table 2 of the publication. Scattering and clouds are neglected. Included CIA pairs:  
N2-N2, N2-O2, O2-O2.  
  
All spectra assume the Earth-twin to orbit a G2V star (Sun-like) on a circular 1AU orbit   
at a distance of 10pc from the observer.  
  
  
## Description of the different subdirectories:  
  
  
- `R_SNR_WL_Grid/`  
	Contains the 96 different LIFEsim spectra used in the grid retrievals (Section 4.2 in publication), and the 8 Photon noise spectra used for the the Detection limit analysis (Section 4.1 in publication).  
  
- `R50_SNR10_Noisy/` 
	Contains the 20 different noise realizations of the LIFEsim spectrum used for the study presented in Appendix C of the publication.  
  
- `R1000_SNR50_Validation/` 
	Contains the high resolution spectrum used in the retrieval validation (Section 3 in publication) and the Detection limit analysis (Section 4.1 in publication).  
  

## Structure of the filenames in the subdirectories:  
     
  
```  
<NoiseName>_R<Resolution>_SNR<S/N>_wlen<Coverage><NoiseScenario>.txt  
```  
  
  
- **NoiseName**   
   Assumed Noise scenario. Values:  
      - `Photon`: Only photon noise of the source. Flux not randomized.  
      - `LIFE`: LIFEsim noise. Flux not randomized.  
      - `LIFE_NoisyXX`: LIFEsim noise. Flux randomized. XX: number of the realization.  
  
- **Resolution**: Resolution of the spectrum. Values: `20`, `35`, `50`, `100`, `1000`.  
  
- **S/N**: S/N of the spectrum in the 11.2 micron bin. Values: `5`, `10`, `15`, `20`, `50`.  
  
- **Coverage**: Wavelength coverage of spectra in micron. Values: `3_20`, `4_18.5`, `6_17`.  
  
- **NoiseScenario**: Noise settings for LIFEsim (see Section 4.2 in publication). Values:  
      - `None`: "Nominal case".  
      - `_opt`: "Optimized case".  
  
  
  
## Structure of the files in the subdirectories:  
  
Each file contains the following 3 columns:  
  
  
``` 
	First Column      Second Column         Third Column           
	Wavelengths      Flux at 10 pc       Noise on Flux at 10 pc  
	[micron]       [erg s-1 Hz-1 m-2]     [erg s-1 Hz-1 m-2]
      
```