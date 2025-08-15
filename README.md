# _P. falciparum_ _var_ DBLalpha PCR

For _var_ genotyping, a sequence region within the _var_ genes encoding the Duffy-binding-like alpha (DBLα) domain of _Plasmodium falciparum_ erythrocyte membrane protein 1 (PfEMP1) are amplified in a single-step PCR from genomic DNA (gDNA) using universal degenerate primer sequences. These primers originally described by [Taylor et al. (2000)](https://www.sciencedirect.com/science/article/pii/S0166685199001590?via%3Dihub) and modified by [Bull et al. (2005)](https://journals.plos.org/plospathogens/article?id=10.1371/journal.ppat.0010026) amplify a ~450 bp fragment known as a **DBLα tag** ([Rask et al. 2016](https://pubmed.ncbi.nlm.nih.gov/27102804/)).
* Forward primer: DBLαAF, 5’-GCACGMAGTTTYGC-3’
* Reverse primer: DBLαBR, 5’-GCCCATTCSTCGAACCA- 3’

The DBLαAF and DBLαBR primers target homology blocks D and H, respectively (as per [Smith et al. 2000](https://pubmed.ncbi.nlm.nih.gov/11071284/)) or homology blocks 2 and 3, respectively (as per [Rask et al. 2010](https://pubmed.ncbi.nlm.nih.gov/20862303/)).

For details on the validation of these primers for amplification of DBLα sequences of the appropriate length (~450 bp) using _P. falciparum_ reference strains (3D7, Dd2, and HB3) see [Rask et al. 2016](https://pubmed.ncbi.nlm.nih.gov/27102804/).
 
Provided below is an overview of the laboratory protocol for the targeted amplicon sequencing of these DBLα tags, known as varcoding ([Tiedje et al. 2023](https://pubmed.ncbi.nlm.nih.gov/37292908/) and [Day et al. 2025](https://pubmed.ncbi.nlm.nih.gov/40393890/)). A suite of [bioinformatics tools and pipelines](https://github.com/UniMelb-Day-Lab/tutorialDBLalpha) have been developed by the Day Lab at The University of Melbourne to process amplified **DBLα tags** into reference **DBLα types** and perform subsequent downstream analyses.

## PCR Protocol
This single-step PCR protocol was optimized to maximize amplification success, particularly when working with dried blood spot (DBS) samples collected from participants with low-density _P. falciparum_ infections.  

The single-step PCR was carried out in a total volume of 40 μL, comprising 2 µL of gDNA template, with final concentrations of 0.5X buffer, 2 mM of MgCl₂, 0.07 mM of dNTP mix (Promega), 0.375 μM of each primer (DBLαAF and DBLαBR; [Version 1](https://github.com/UniMelb-Day-Lab/Pfalciparum_varDBLalpha_PCR/blob/main/Appendix%201%20Version%201%20DBLa%20Primers.pdf) or [Version 2]()), 3 units of GoTaq G2 Flexi DNA polymerase (Promega), and nuclease-free water.

* For details on the [Version 1](https://github.com/UniMelb-Day-Lab/Pfalciparum_varDBLalpha_PCR/blob/main/Appendix%201%20Version%201%20DBLa%20Primers.pdf) and [Version 2]() DBLαAF and DBLαBR primers, please see below.


#### Table 1. PCR mastermix.
| Reagent                    | Final Concentration | Volume 1X |
|----------------------------|---------------------|-----------|
| Buffer (5X)                | 0.5X                | 4 μL      |
| MgCl₂ (25 mM)              | 2 mM                | 3.2 μL    |
| dNTP mix (2 mM)            | 0.07 mM             | 1.4 μL    |
| Primer DBLαAF (10 μM)      | 0.375 μM            | 1.5 μL    |
| Primer DBLαBR (10 μM)      | 0.375 μM            | 1.5 μL    |
| GoTaq G2 Flexi (5 U/μL)    | 3 units             | 0.6 μL    |
| Nuclease-free water        |                     | 25.8 μL   |
| gDNA Template              |                     | 2 μL      |
| **TOTAL VOLUME**           |                     | **40 μL** |


#### Cycling conditions:
* 95ᵒC for 2 min
* 30 cycles of
   * 95ᵒC for 40 sec
   * 49ᵒC for 90 sec
   * 65ᵒC for 90 sec
* 65ᵒC for 10 min
* storage at 4°C

_Note: For each PCR, positive (e.g., P. falciparum 3D7, Dd2, and/or HB3 reference strains) and negative (i.e., nuclease-free water) controls were included for quality control._


## Next Steps (post-PCR)
1) PCR products were purified using the [SPRI method](https://www.mybeckman.com/resources/technologies/spri-beads) (solid-phase reversible immobilization) (AMPure XP Beads, Beckman Coulter).
2) Purified PCR product concentrations were measured using the [Quant-iT PicoGreen dsDNA kit](https://assets.thermofisher.com/TFS-Assets/LSG/manuals/mp07581.pdf) as per the manufacturer’s instructions (Invitrogen). We assayed fluorescence intensity using a Perkin-Elmer VICTOR X3 multilabel plate reader, with fluorescein excitation wavelength of ~480 nm and emission of ~520 nm wavelength.
4) Amplicons were then pooled equimolarly with each pool consisting of up to 106 isolates, all with unique multiplex identifier (MID) tags.
5) Pooled amplicons were subsequently indexed (Amplicon Indexing Service) and sequenced on an Illumina platform using the MiSeq Reagent Kit v3 (600 cycle; 2×300bp paired-end).


## Version 1 DBLαAF and DBLαBR Primers
For Version 1 the universal degenerate primers (i.e., forward primer: DBLαAF and reverse primer: DBLαBR) were coupled with a GS FLX Titanium primer sequence (i.e., adaptor). In addition, both the forward and reverse primers were barcoded with a unique 10 bp multiplex identifier (MID) tag ([Roche, 2009](https://www.scribd.com/doc/316505708/The-GS-FLX-Titanium-Chemistry-Extended-MID-Set-Copia)) for multiplexed sequencing.

> Example forward primer: **DBLαAF-MID-1**:     5'-(adaptor)(key)(MID)(DBLα AF forward primer)-3'
>```
> 5'-(CGTATCGCCTCCCTCGCGCCA)(TCAG)(ACGAGTGCGT)(GCACGMAGTTTYGC)-3'
>```
> Example reverse primer: **DBLαBR-MID-1**:     5'-(adaptor)(key)(MID)(DBLα BR reverse primer)-3'
>```
> 5'-(CTATGCGCCTTGCCAGCCCGC)(TCAG)(ACGAGTGCGT)(GCCCATTCSTCGAACCA)-3'
>```

* For a complete list of the 106 Version 1 DBLαAF and DBLαBR primer sequences, see [**Appendix 1**](https://github.com/UniMelb-Day-Lab/Pfalciparum_varDBLalpha_PCR/blob/main/Appendix%201%20Version%201%20DBLa%20Primers.pdf).
* The use of the GS FLX Titanium primer sequence (i.e., adaptor) in the Version 1 primers is a remnant of previous work and is being phased out. We are currently shifiting to using the updated Version 2 primers described below.

### Citations for the Version 1 primers

These Version 1 primers have been used in the following citations:
* Day KP, Artzy-Randrup Y, Tiedje KE, Rougeron V, Chen DS, Rask TS, Rorick MM, Migot-Nabias F, Deloron P, Luty AJF, Pascual M. Evidence of strain structure in Plasmodium falciparum var gene repertoires in children from Gabon, West Africa. Proc Natl Acad Sci U S A. 2017 May 16;114(20):E4103-E4111. doi: 10.1073/pnas.1613018114. Epub 2017 May 1. Erratum in: Proc Natl Acad Sci U S A. 2024 Apr 9;121(15):e2404410121. doi: 10.1073/pnas.2404410121. PMID: 28461509; PMCID: PMC5441825. (https://pubmed.ncbi.nlm.nih.gov/28461509/)
* Rougeron V, Tiedje KE, Chen DS, Rask TS, Gamboa D, Maestre A, Musset L, Legrand E, Noya O, Yalcindag E, Renaud F, Prugnolle F, Day KP. Evolutionary structure of Plasmodium falciparum major variant surface antigen genes in South America: Implications for epidemic transmission and surveillance. Ecol Evol. 2017 Oct 8;7(22):9376-9390. doi: 10.1002/ece3.3425. PMID: 29187975; PMCID: PMC5696401. (https://pubmed.ncbi.nlm.nih.gov/29187975/)
* Ruybal-Pesántez S, Tiedje KE, Tonkin-Hill G, Rask TS, Kamya MR, Greenhouse B, Dorsey G, Duffy MF, Day KP. Population genomics of virulence genes of Plasmodium falciparum in clinical isolates from Uganda. Sci Rep. 2017 Sep 18;7(1):11810. doi: 10.1038/s41598-017-11814-9. Erratum in: Sci Rep. 2024 Sep 30;14(1):22717. doi: 10.1038/s41598-024-72799-w. PMID: 28924231; PMCID: PMC5603532. (https://pubmed.ncbi.nlm.nih.gov/28924231/)
* Ruybal-Pesántez S, Sáenz FE, Deed SL, Johnson EK, Larremore DB, Vera-Arias CA, Tiedje KE, Day KP. Molecular epidemiology of continued Plasmodium falciparum disease transmission after an outbreak in Ecuador. Front Trop Dis. 2023;4:1085862. doi: 10.3389/fitd.2023.1085862. Epub 2023 Mar 16. PMID: 39525803; PMCID: PMC11546077. (https://pubmed.ncbi.nlm.nih.gov/39525803/)
* Ruybal-Pesántez S, Tiedje KE, Pilosof S, Tonkin-Hill G, He Q, Rask TS, Amenga-Etego L, Oduro AR, Koram KA, Pascual M, Day KP. Age-specific patterns of DBLα var diversity can explain why residents of high malaria transmission areas remain susceptible to Plasmodium falciparum blood stage infection throughout life. Int J Parasitol. 2022 Oct;52(11):721-731. doi: 10.1016/j.ijpara.2021.12.001. Epub 2022 Jan 31. PMID: 35093396; PMCID: PMC9339046. (https://pubmed.ncbi.nlm.nih.gov/35093396/)
* Tan MH, Tiedje KE, Feng Q, Zhan Q, Pascual M, Shim H, Chan YB, Day KP. A paradoxical population structure of var DBLα types in Africa. PLoS Pathog. 2025 Feb 4;21(2):e1012813. doi: 10.1371/journal.ppat.1012813. PMID: 39903780; PMCID: PMC11793742. (https://pubmed.ncbi.nlm.nih.gov/39903780/)
* Tiedje KE, Zhan Q, Ruybal-Pésantez S, Tonkin-Hill G, He Q, Tan MH, Argyropoulos DC, Deed SL, Ghansah A, Bangre O, Oduro AR, Koram KA, Pascual M, Day KP. Measuring changes in Plasmodium falciparum census population size in response to sequential malaria control interventions. medRxiv [Preprint]. 2025 Jun 17:2023.05.18.23290210. doi: 10.1101/2023.05.18.23290210. PMID: 37292908; PMCID: PMC10246142. (https://pubmed.ncbi.nlm.nih.gov/37292908/)


## Version 2 DBLαAF and DBLαBR Primers
For Version 2 the universal degenerate primers (i.e., forward primer: DBLαAF and reverse primer: DBLαBR) were coupled with Illumina Nextera overhangs, to facilitate subsequent preparation of sequencing libraries. In addition, the forward primers were barcoded with a unique 10 bp multiplex identifier (MID) tag ([Roche, 2009](https://www.scribd.com/doc/316505708/The-GS-FLX-Titanium-Chemistry-Extended-MID-Set-Copia)) for multiplexed sequencing, while the reverse primers were unbarcoded.

> Example forward primer: **DBLαAF-MID-1.v2**:     5'-(Forward Nextera overhang)(MID)(DBLα AF forward primer)-3'
>```
> 5'-(TCGTCGGCAGCGTCAGATGTGTATAAGAGACAG)(ACGAGTGCGT)(GCACGMAGTTTYGC)-3'
>```
> Example reverse primer: **DBLαBR.v2**:     5'-(Reverse Nextera overhang)(DBLα BR reverse primer)-3'
>```
> 5'-(GTCTCGTGGGCTCGGAGATGTGTATAAGAGACAG)(GCCCATTCSTCGAACCA)-3'
>```

* For a complete list of the 106 Version 2 DBLαAF and DBLαBR primer sequences, see [**Appendix 2**](). 

### Citations for the Version 2 primers

These Version 2 primers have been used in the following citations:

* Tan MH, Bangre O, Rios-Teran CA, Tiedje KE, Deed SL, Zhan Q, Rasyidi F, Pascual M, Ansah PO, Day KP. Metagenomic analysis reveals extreme complexity of Plasmodium spp. infections in high transmission in West Africa. medRxiv [Preprint]. 2025 May 2:2025.04.29.25326533. doi: 10.1101/2025.04.29.25326533. PMID: 40343031; PMCID: PMC12060935 (https://pubmed.ncbi.nlm.nih.gov/40343031/)
