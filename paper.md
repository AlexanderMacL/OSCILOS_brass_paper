---
title: 'OSCILOS_brass, an acoustic solver for brass instruments'
tags:
  - brass instruments
  - acoustics
  - aeroacoustics
  - musical acoustics
  - MATLAB
authors:
  - name: Alexander MacLaren
    orcid: 0000-0002-5835-216X
    affiliation: 1
  - name: Renaud Gaudron^[Corresponding author: r.gaudron@imperial.ac.uk]
    affiliation: "1, 2"
affiliations:
 - name: Imperial College London
   index: 1
 - name: Aimee Morgans, Professor of Thermofluids, Dept. Mechanical Engineering, Imperial College London
   index: 2
date: 10 October 2020
bibliography: paper.bib

---

# Summary

 The sound, or timbre, of musical instruments is controlled by the 
 balance and tuning of their modal frequencies, or harmonics. In brass 
 instruments like the trumpet, french horn and trombone, the geometry 
 of the internal bore is the principal factor determining the modal 
 frequencies. Harmonic analysis of brass instruments is necessary to 
 assist bore shape optimisation by instrument makers, and to enable 
 research into lip dynamics, the origins of 'brassiness', and other 
 prevailing questions in brass wind acoustics. 


# Statement of need

OSCILOS_brass provides an easy-to-use platform for determining the 
resonant modes of a given instrument geometry, be it drainpipe or tuba. OSCILOS_brass is based on 
OSCILOS_long [@Li2017], the open-source combustion instability low-order 
simulator (longditudinal), an open source code for simulating 
combustion instability. It is written in MATLAB, is highly modular, and 
is straightforward to run and edit. It represents an instrument bore as 
a sequence of connected cylindrical finite elements, using a 1-D plane wave approximation. A variety of inlet and exit acoustic 
boundary conditions are available, including open, closed, 
Levine-Schwinger and user-defined boundary conditions. The mean flow is 
calculated assuming 1-D flow conditions, with changes only 
across element interfaces. The current release is for longitudinal 
modes only.

A typical tenor trombone geometry is shown in Fig. \autoref{fig:geom}.

![Trombone bore profile from [@Bilbao2013] as represented by OSCILOS_brass\label{fig:geom}](figures/TromboneGeometry.png)

OSCILOS_brass calculates the Equivalent Fundamental Pitch deviation 
defined by [@Chick2004], according to \autoref{eqn:EFP}, where 
$f_i$ is the frequency of the $i$th mode, and $F$ is the reference 
fundamental pitch, conventionally taken as $f_4/4$, the note to which 
brass players often tune their instruments. The unit of this definition 
is the \verb|[cent]|, equal to $1/100$th of a semitone, or a frequency 
ratio of $\sqrt[1200]{2}$. EFP is shown for 4 combinations of boundary 
conditions in \autoref{fig:trombBC}, as calculated by OSCILOS_brass for 
the above trombone geometry.

\begin{equation}\label{eqn:EFP}
	\mathrm{EFP}(f_i) = \frac{1200}{\log(2)}\log\left[\frac{f_i}{iF}\right]
\end{equation}

![EFP output by OSCILOS_brass for 4 sets of boundary conditions applied to the trombone geometry from [@Bilbao2013]](figures/TromboneBCsEFP.png)

Good agreement with published measurements and simulations for this geometry is shown in Fig. \autoref{fig:tromb}. Comparison to Tuba measurements obtained by a separate study is shown in \autoref{fig:tuba}

![OSCILOS_brass EFP comparison to results for trombone geometry from [@Bilbao2013]\label{fig:tromb}](figures/TromboneEFP.png)
![OSCILOS_brass EFP comparison to results for tuba geometry from [@Norman2013]\label{fig:tuba}](figures/TubaEFP.png)

# Acknowledgements

This work was supported in part by the European Research Council (ERC) 
Consolidator Grant AFIRMATIVE (2018–2023). A. MacLaren acknowledges the 
Mechanical Engineering UROP Bursary 2020 from Imperial College London.

# References
