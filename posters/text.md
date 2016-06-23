# Structure:

1. Introcution (obviously)
1. Methods

    - Starting Model (LPX)
    - Benchmarking System
    - Model Evaluation
    - Data driven development
    - Re-evalutation
    - Application

1. Conclusion
1. Acknoledgments


# Introduction

- Show example re-paramterixation of already incorporated process and inclusing of new proreces.

## Old-school model development

- Focussed on incorporating sub-model rather than parameterization
- Model tuning to get right results with wrong process-representation
- No test for model degradation
- Unknown "uncertainty" in model results
- Hard to understand drivers of change for e.g. future predictions
- Due to a lack of comprehensive benchmarking system


## New approuch model development

- Call from community for more comprehensive model evaluation (e.g CEHs JULES, cLamb, iLamb)
- Recent advances in remote sensing and communications means there is a lot more data
- Develop a benchmark system to:

    - Find model weaknesses
    - Assess model development
    - Justify model application

- Data-driven model parameterization

# Circle

## Initial Model

- LPX (prentice et al. 2011) is a coupled fire-dynamic global vegetetaion model
- Developed at a global level
- As the last around of model development was to incorporate a fire model assessed against burnt area and fire carbon flux observations globally.

## Benchmarking

- The benchmarking system (right) was used to identifty specific weaknesses of the model, in specific locations.
- Despite an overall good performance in fire, weakness in other aspects of the model suggestes fire performance could be for "the wrong reasons"
- Fire is poorly simulated in Tropical Savanna and dry woodland areas, particularly for Australia.
- Extra data (e.g. satalite post-fire vegetation recovery time) and simple model comparisons (e.g. GLM results for fire controls) were used to evaluate <<>> leading to weaknesses in individual processes).

## Model evaluation
- statistics used to quantify and compare across processes
- identified two areas of key weakness for simulting fire regimes in Australia:
    
    1. Fire performs "worse than mean" (although still "better than random"
    1. Balance of "controls" on fire - e.g. fire ignitions (from Lightning Source) dominant, resultingin an MM score "worse than random"
    1. Rapid forest-grassland boundries corrispons to fire boundries means vegetation cover is "as good as random", suggesting too much tree mortality to fire
    1. Model expreiments show extremely slow post-fire recovery of woody vegetation compared to observations.

## Data Analysis
- Analysis of observational data used to re-parameterize different processes contributing to error in controls on fire:

    - Lightning scheme - ignitions (shown)
    - root profiles - fuel loads
    - fuel decompositing - fuel loads
    - fuel drying time - moisture

- Also used to develope vegetqation fire traits for woody vegetation surival

   - Evolving Bark thickness for proection
   - Post-disturbance resprouting for recovery 

## Model development
- Extra Benchmarking imformation used again to assess new processes (e.g. Model improvment in model revovery time) (in bit above title?)
- Recovery time split between RS and NR ecosystems and compared to model experiments for simulated RS and NR vegetation cover
- Re-analysing controls on fire shows better balance between fuel and moisture vs ignitions
- Scalability of metric scores means we can demonstrate and %% impovment in simulated fire
- Woody fire adpations imporve simulated vegetation by ...


## Application 
- For the application of impact of changing climate on carbon stocks, used ... (check submitted paper)

# Benchmarking System

## Datasets

- "Standard" package come with datasets to evaluate multiple key processes:
    - Vegetation Cover - Tree/grass cover, phenology and lead type
    - Fire - Burnt area
    - Photosynthesis - fAPAR
    - Height
    - Production - GPP and NPP
    - CO<sub>2</sub> fluxes - Seasonal variations and inter-annual growth
    - Hydrology - river catchment runoff

- More datasets are still being added (e.g. carbon pools, fire intensity, number of fires; Hanston et al. in prep)
- Allows for incorporation of other data types, or statistical model results if required (see examples)

## Metrics

- Uses specifically designed metrics to quantify differences between model and observation


## Null models
- Title: Score interpretation

- Lower scores are better, 0 being perfect
- infinity, 2 and 1 are worse scores for NME, MM and MPD respectivly. 
- Two NULL models developed to further aid inpretpetation of metric score
- Mean Model compares the mean to the spread of the obsvertations using the metric. Scores lower than this are "better than mean"
- The resampled model compares 1000 bootstraps of randomly resampled observations to produce a probablity distribution of "random model" scores. Scores lower than this distrbution are "better than randomly resampled", within the distribution are "as good as random", and great than the distributuon are "worse than random".
 


## Application

- Quantify how well a model performs across a comprehensive range of important processes
- Allows identification of model weaknesses and processes that require improvement
- Quantifies the differences between model version and impact of new parameterizations
- Allows model inter-comparison

-adopted an explicit iterative approach to model development in the Land Processes and eXchanges (LPX: \citealp{Prentice2011}) dynamic global vegetation model (DGVM), in which benchmarking against observations is used to identify areas for new data-driven parameterizations and then subsequently used to evaluate whether the implementation of these new parameterizations produces an overall improvement in model performance.

-contrasts with the general tendency to focus evaluation on new components, for example the evaluation of fire treatments within DGVMs using only observations of burnt area and/or fire carbon fluxes  \citep[see e.g.][]{Li2012,Pfeiffer2013}. One reason for this partial approach to evaluation is the lack of a comprehensive benchmarking system \citep{Luo2012}.

- Existing attempts to develop benchmarks for the evaluation of DGVMs and land-surface surface models have focused on a limited number of processes, generally related to energy and carbon fluxes \citep[e.g.][]{Randerson2009,blyth2010evaluating,Beer2010,cadule2010benchmarking,blyth2011comprehensive}. Furthermore, they make use of a limited number of metrics which are difficult to compare across processes and do not yield results that are easily interpreted in terms of the causes of model errors. As part of this thesis (Chapter 2), I have developed a comprehensive benchmarking system which allows evaluation of spatial and temporal patterns of multiple aspects of the simulated vegetation, hydrology, fire regimes and ecosystem fluxes as well as allowing the impact of specific types of bias to be taken into account. This benchmarking system serves several purposes: (1) it quantifies how well a model performs across a comprehensive range of important processes; (2) it allows the identification of model weaknesses through comparison of the performance with respect to different benchmarks and thus facilitates the identification of processes that require improvement; (3) it quantifies the differences between model versions, which allows assessment of the overall impact of new parameterizations. Application of this benchmarking system to LPX identified Australia as a region that was poorly simulated compared to other parts of the world. One reason for this was the sharp, fire-controlled boundaries between grassland and forest. Through benchmarking, I identified that the sharp boundaries between regions experiencing no fire and those experiencing fire resulted from an unrealistic sensitivity to lightning ignitions. This led to the re-examination of lightning parameterization (Chapter 4). The sharp grassland/forest boundaries resulted because of high mortality rates for woody plants in areas with fire. This led to a re-examination of the realism of the PFT-specific treatment of bark thickness in the model and the subsequent inclusion of an adaptive parameterization of bark thickness as well as fire recovery through resprouting in the model (Chapter 4).

The implementation of individual data-driven parameterizations can degrade model performance, particularly when the original parameterization was tuned to produce a reasonable simulation of an emergent property of the model.  For example, in the original version of LPX, the parameterization of lighting distribution on wet and dry days was tuned to produce a good simulation of burnt area \citep{Prentice2011}. The implementation of a new treatment based on analyses of the actual occurrence of lightning on days with/without rain resulted in a significant increase in the amount of fire and led to a 24\% degradation in the simulated annual average burnt area in Australia. However, benchmarking showed that the new parameterization resulted in a 7-8\% improvement in the seasonal pattern of fire and a more realistic timing of the peak fire season by between 15-22 days. The fact that the benchmarking system was specifically set up to measure different aspects of the fire regime meant that it was possible to distinguish between the bias in total fire and the simulation of a more realistic temporal pattern of fire, and thus to isolate the causes of the overall bias as resulting from poor simulation of burnt area rather than ignitions. Once new parameterizations effecting fuel loads and moisture were implemented, the bias in total burnt area was reduced, resulting in a 19\% overall improvement in model performance.

The model development described in this thesis was driven by extensive data analysis, and can be seen as part of a wider movement towards data-driven parameterization of a wide range of fundamental vegetation processes \citep[see e.g.][]{Brovkin2012,smith2012climate,Wang2012b,Wang2013a,Verheijen2013,Prentice2014,Wang2014}. The initial development of DGVMs and fire-enabled DGVMs occurred when access to large-scale or multi-year data sets was limited. Many of the early models were developed using studies from specific regions: MC-FIRE \citep{Lenihan1998} for example was initially developed using data from studies in South Dakota, while GLOBFIRM \citep{Thonicke2001} was parameterized using data from 31 sites from Portugal, California and northern Australia. However, the increasing availability of remotely-sensed data sets or GIS-based data products provide a fantastic opportunity for data-driven model development. The parameterization of lighting ignitions in this thesis provides an example, since it was based on an analysis of remotely-sensed lightning observations \citep[LIS;][]{Christian1999,Christian1999a} , together with extensive ground-based observations of lightning \citep[NDLN;][]{Cummins2009} and daily precipitation data \citep[CPC;][]{Higgins1996,Higgins2000a} at a continental scale over the USA. 

The collation of site-based or field data in databases provides another source of information for data-driven model development. In this thesis, I made use of the TRY database of plant traits \citep{Kattge2011}, for example, to obtain data on bark thickness for individual species. However, data syntheses of this sort are relatively new and existing databases do not cover all areas of interest for model development. In this thesis, I present an analysis of a new database of fire-response traits (Chapter 3). This work was a contribution to the Australian Centre for Ecological Analysis and Synthesis (ACEAS) working group on `Using plant functional traits to predict ecosystem vulnerability to changing fire regimes' (\url{www.aceas.org.au/index.php?option=com_content&view=article&id=114&Itemid=115}), part of the aim of which is to synthesise data about fire-related plant traits. This effort could provide a rich source of information that could be used in future model development. There are many other areas where synthesis of site-based data could potentially be useful for model development. One example would be the synthesis of sited-based data on fuel loads, which could be used to characterize the relationship between fuel limitation and fire --- something that fire-enabled DGVMs handle very differently (see Table 1.1). Similarly, data on wind profiles in different vegetation types could help improve the scaling of wind speed data to take account of the presence of vegetation in models. 
 
One novel aspect of the model development undertaken in this thesis is the inclusion of within-PFT variability in bark thickness in LPX (Chapter 4).  In many DGVMs the basic vegetation unit is a PFT, with PFT-specific values for individual parameters and simulated vegetation represented by an average individual plant per PFT within a given grid cell. However, there is considerable variability in the characteristics of the individual plant species that are grouped together, for simplicity, within any PFT. This variability underpins species selection in response to changing environmental conditions. Bark thickness is a classic example of this: thicker-barked species are more likely to survive a fire and thus there is selective pressure toward these species in fire prone regions such that the average bark thickness within a population increases with fire frequency \citep[Fig.~\ref{Intro_f7}][]{Lawes2011a}. Here, I have adopted the method for incorporating within-PFT trait variability described by \citet{Verheijen2013} and applied it to bark thickness (Fig. 4.5). Bark thickness within each PFT is initially represented by a simple data-derived distribution. Fire preferentially kills the thinner barked individuals within this distribution. The post-fire distribution is calculated based on the average bark thickness of surviving and re-establishing individuals.  This scheme allows representation of the full range of bark thickness found within each PFT, and allows the PFT-averaged bark thickness to adapt to changes in fire regime, but does not increase model complexity excessively and avoids the need to add additional computationally expensive PFTs in order to describe the range of trait variability better. Within-PFT variability exists in other simulated traits (e.g. the fraction of deep roots: Fig 4.3) and field observations suggest that these characteristics can also be adaptive \citep[e.g. the increase in average rooting depth along aridity gradients][]{Schenk2002a,Schenk2002,Schenk2005}. Adaptive parameterization of such traits could provide substantial improvements to the simulation of vegetation responses to climate change. However, the design of such a parameterization requires an understanding of the adaptive benefit conferred by changes in the trait, as well as the existence of site-based data syntheses in order to develop well-founded parameterizations.

Another novel aspect of this thesis is the incorporation of resprouting PFTs in order to improve the post-fire response of woody vegetation (Chapter 4). The initial suite of PFTs in DGVMs was chosen to allow the representation of climate and environmental controls on vegetation distribution and carbon cycling. Additional PFTs have been added as new processes were incorporated in the DGVM framework. For example, the inclusion of wetlands in LPJ in order to improve the simulation of the terrestrial carbon and methane cycles necessitated the creation of two new PFTs, specifically mosses and flood tolerant grasses \citep[LPJ-WhyMe:][]{Wania2007,Wania2010}. Similarly, crop PFTs were incorporated into LPJ in order to simulate human land use \citep[LPJ-ml:][]{Bondeau2007} and a shrub PFT was included in CLM-DGVM to improve the simulation of arid/semi-arid shrublands \citep{Zeng2008}. Despite the fact that many vegetation types are maintained by regular fire \citep[e.g. savannas:][]{Cochrane1999,beckage2009vegetation,Lehmann2011} and that plants in fire-prone ecosystems display adaptations to survive or recover quickly after fire \citep{Clarke2013}, there has been no consideration of the need to include fire-related PFTs in a DGVM framework until now. Resprouting, the ability to regenerate from meristems in wood, bark or underground organs, is typical of fire-adapted vegetation. This behavior has a significant implication for the carbon cycle. Post-fire recovery rates in the current generation of DGVMs and land-surface models are slow because plants have to regenerate from seed. The ability to resprout means that ecosystem recovery takes place much faster (Fig. 4.7). I used analyses of site-based abundance data on resprouting (Chapter 3) to identify which PFTs included both resprouters and non-resprouters. This led to the definition of for new PFTs: resprouting tropical broadleaf evergreen trees, resprouting tropical broadleaf deciduous trees, resprouting temperate broadleaf evergreen trees, resprouting temperate broadleaf deciduous trees. Further data analyses allowed me to derive a cost for resprouting in terms of a reduction in reproductive success and establishment from seeds (Chapter 4). This treatment leads to a situation in which resprouting is favoured in fire-prone areas but resprouting trees are less successful after other forms of disturbance. Thus, the relative abundance of resprouting trees and non-resprouting trees is responsive to changes in fire regimes. The inclusion of resprouting PFTs and adaptive bark thickness in LPX produces a 33\% improvement in the simulated vegetation distribution across Australia (Chapter 4).

The reduced re-seeding rate in resproutiung pfts compared to their non-resprouting counterparts represents an initial attempt to model a resprouting trade-off - regeneration via resprouting is at the expensive of new seedling establishment. Another important consideration, which we have not attempted to model, is the cost in carbon for building and maintaining resprouting and thick bark adaptations.  Thicker bark requires greater carbon investment and resprouters have a higher allocation to roots than shoots \citep[see e.g.][]{knox2005effects} and non-structural carbohydrate stores in order to “fund” resprouting  \citep{Clarke2013}. This carbon must be diverted from other plant structures, which is likely to cause decrease juvenile growth rates and increase the time for plants to reach sexual maturity \citep{bell1999underground,lamont2003seed,Lawes2011a,Clarke2013} as well as decreasing reproductive success. Including these costs in a modelling framework would improve the representation of competition between fire adaptive (thick barked/resprouting) and non-fire adapted (thin barked/non-resprouting) PFTs. However, as of yet, there have been very few attempts to quantify these costs in a way that would allow them to be modelled.

The overarching goal of this thesis was to produce a model that provides a good representation of fire across Australia in order to be able to use it for future prediction. LPX-Mv1 incorporates improvements to the simulation of ignitions, fuel loads, fuel drying rates, fire resistance, and fire recovery rates (Chapter 4). The simulated distribution of vegetation and fire is significantly improved compared to the original version of LPX. I have applied this model to examine changes in fire regimes over the 21\textsuperscript{st} century in response to projections of future climate changes (Chapter 5). Previous studies, based on calculation of some form of Fire Danger Index (FDI), have shown that the risk of fire increases across the whole of Australia in the 21\textsuperscript{st} century \citep{Beer1995,Williams2001,mcgregor2001csiro,Pitman2007}. However, FDIs only take account of the prevalence of climate conditions that favour burning. They do not take account of the potential for CO\subscript{2} fertilization or climate-induced changes in vegetation on fuel production or structure. The LPX-Mv1 simulations show that climate-induced increases in fire risk do not necessarily translate into increases in biomass burning. The simulations imply that fire will decrease in northern Australia and increase in the interior and southeastern parts of the continent. The reduction of fire in northern Australia occurs because of increased fuel moisture and decreases in wind speed during the fire season. The increase of fire in southeastern Australia occurs because of an increase in fuel dryness in a region where fires are currently moisture-limited. The increase in fire in the interior of the continent reflects increases in fuel load in an area that is currently fuel-limited. Some of these changes reflect changes in vegetation productivity as a result of CO\subscript{2} fertilization. Thus, despite an increase in aridity, grass productivity is enhanced in the interior and this leads to greater fuel production and reduction of the area that is fuel limited. CO\subscript{2} fertilization is also responsible for the expansion of woody resprouting PFTs into relatively dry environments, which affects fuel load, structure and moisture conditions. However, the simulated expansion of woody vegetation is only possible because of the inclusion of resprouting PFTs in the model. In the absence of these fire-adapted trees, increased productivity would lead to increased fire and the replacement of trees by grasses. The maintenance of a significant tree cover, and indeed expansion of tree cover into many fire-prone regions, combined with the rapid recovery of biomass after fire due to resprouting, results in a 10\% increase in carbon sequestration by the biosphere over the 21\textsuperscript{st} century despite an increase in the overall amount of fire at a continental scale. This is a novel result which runs counter to inferences that might be made about the carbon budget of Australia based on changing fire danger indices or indeed DGVMs that lack realistic treatments of vegetation adaptations to fire. 

