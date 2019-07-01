# Project-Southern-Apps-History

Across many landscapes, the processes that generated contemporary vegetation patterns are poorly understood due to insufficient historical data.  The southern Appalachians in the southeastern United States exemplify this conundrum:  Although the canopy is currently dominated by oaks, oak regeneration is limited.  A clear understanding of the processes that generated the current oak canopy – and that limit oak regeneration today - is necessary for making decision about how to manage oaks into the future.  We used a landscape simulation approach to generate a historic analog of the landscape beginning in 1500 CE and simulated forward to 2000 CE, and included estimates of critical processes and events:  Native American burning up to ~1800; colonial settlement and burning from 1800-1900; the loss of chestnut (Castanea dentata), a keystone species, due to blight around 1940; and fire exclusion beginning in 1930.  Our simulations suggest that although fire is necessary to maintain regeneration across the landscape, it was the sudden loss of chestnut that created a unique opportunity for oak dominance across the landscape.  The extent of oak dominance today is likely a millennial maximum for the species.  Future oak dominance at the current extent would require more fire than would be acceptable given human settlement patterns although local efforts at reintroducing prescribed fire can maintain this critical species.

# Methods

## Initial Communities

Initial communities for the southern Appalachians was constructed through the use of imputed forest basal area maps developed by the U.S. Forest Service to a resolution of 250 meters across the eastern United States (Wilson et al. 2013). Biomass estimates for these communities were conducted using data from the Forest Inventory and Analysis database of the U.S. Forest Service. This process used FIA_TREE table data to identify the most important tree species on the landscape. This list was reduced to the 48 most important species as they accounted for 99% of the basal area of the landscape. Plot data for the biomass of species-age cohorts was then associated to similar cells in the Forest Service imputation maps based on Sorenson's similarity index. For more information, contact Zachary Robbins at zjrobbin@ncsu.edu.

To estimate the forest community of the landscape in 1800, we simulated the landscape using LANDIS-II model for 250 years simulating Native American burning frequency (Lafon et al., 2017) using the Base Fire extension (He & Mladenoff, 1999). Succession was simulated using the Net Ecosystem Carbon and Nitrogen expension (Scheller et al. 2011). To simulate the prevalence of chestnuts on this landscape, 150 year old cohorts of American chestnuts were added to cells that contained oak species in the initial community. The amount of chestnut added was calibrated so that the community after the 250-year simulation had a prevalence of chestnuts and oaks that was similar to historical estimates of forest composition (Yarnell 1998). This output community was saved as a new initial community using the [Output Biomass Community extension](https://github.com/LANDIS-II-Foundation/Extension-Output-Biomass-Community) and used for modeling scenarios from 1800-2000.

## Climate Modeling

The climate library for this landscape was constructed by associating climate records in the [PRISM](http://www.prism.oregonstate.edu/recent/) dataset with [USGS isobioclimate regions](https://rmgsc.cr.usgs.gov/ecosystems/datadownload.shtml). Climate library was constructed with daily values from 1981 to present For all model runs, each simulated year used a random year in the climate library to apply to the landscape. This means we assumed that the climate of the region in 1981-present is similar to the climate of the region from 1800-1980. For more information, contact Zachary Robbins at zjrobbin@ncsu.edu.

## Soils Modeling

Soil and hydrology maps at the resolution of the model are required to run LANDIS-II. Maps of soil depth, drainage, field capacity, wilting point, percent sand, and percent clay were estimated using data from the U.S. Department of Agriculture's SSURGO database (Soil Survey Staff, 2019).  Soil carbon and nitrogen pools were estimated by associating soil carbon estimates with previously established C:N ratios of the Century model. from the Oak Ridge National Laboratory. Dead surficial and soil wood was estimated using FIA data. All data was resampled and reprojected to match the resolution of the initial communities file. For more information, contact at zjrobbin@ncsu.edu.

## Landscape topography

Elevation elevation, slope, and aspect maps were created through the use of seemless 1/3 arcsecond digital elevation models (DEMs) from the [U.S. Geological Survey's 3D Elevation program](https://viewer.nationalmap.gov/basic/). Elevation, slope, and aspect maps for the region were constructed in ArcMap 10.5.1 then reprojected to model resolution.

## Scenarios

For this study, we examined the effects of three major historical events on the forest compositions of the southern Appalachians:

1. Suppression of fire in 1930s onward
2. A boom in the timber industry that resulted in the clear-cutting of 70% of the landscape from 1900-1930
3. Chestnut blight resulting in the removal of American chestnuts from the landscape from 1930s onward

The timber boom, chestnut blight, as well as pre-timber boom farming clearcuts were simulated using Base Harvest extension (Gustafson et al., 2000). 

Pre-timber farming clearcuts were simulated as clearcutting occuring in areas of the landscape where the slope of the cell <30%. The cutting was constrained to a random selection of stands in these low-slope areas equaling approximately 30% of the landscape. This is to simulate small patch clearcuts for pasture farming by European colonists from 1800-1900. 

The timber boom was simulated as clearcutting of 25% of the landscape per 10-year harvesting timestep from 1900-1930 across the entire landscape. For this model we assumed that timber clearcutting was equally likely across the entire landscape during this timber boom. This mimics the timber boom where approximately 70% of the landscape had been cut prior to the protection of the forests through the creation of National Forests (Yarnell 1998).

The chestnut blight, a fungal infection that led to the functional extinction of American chestnuts in the Appalachian forests, was simulated using Base Harvest. Beginning in 1930s, all simulated live chestnuts were removed from the landscape and was converted into dead biomass.

Fire on the landscape was simulated using the SCRPPLE fire extension (Scheller et al., 2019). Fires were simulated as low-to-moderate intensity prescription fires burning approximately 5% of the landscape in each year. This simulates the fire frequency of the region in pre-colonial and colonial southern Appalachians of a fire return interval of approximately 20 years (Lafon et al. 2017). Fire suppression was simulated by ceasing ignitions of prescription fires beginning in 1930.

For this study, we tested four alternative scenarios:

 - *Historical Events*: All three historical events are simulated as described above.
 - *No Timber Boom*: Forests become immediately protected from cutting beginning in 1900, removing the effect of the timber boom from 1900-1930.
 - *No Chestnut Blight*: Chestnut blight never arrives in the southern Appalachians.
 - *No Fire Suppression*: Fire ignitions continue on the landscape for the entire model run.

## Output Analysis

Model outputs for a

## Inputs and Data Availability

Landscape inputs for each model run are available in this repository in this [link](insert-link-here).

## Citations

Gustafson EJ, Shifley SR, Mladenoff DJ, Nimerfro KK, He HS. 2000. Spatial simulation of forest succession and timber harvesting using LANDIS. Canadian Journal of Forest Research 30:32-43.

He HS, Mladenoff DJ. 1999. Spatially explicit and stochastic simulation of forest landscape fire disturbance and succession. Ecology 80(1):81-99.

Lafon CW, Naito AT, Gissino-Mayer HD, Horn SP, Waldrop TA. 2017. Fire History of the Appalachian Region: A Review and Synthesis. General Technical Report SRS-219. Ashville, NC: U.S. Department of Agriculture, Forest Service, Southern Research Station.

Scheller RM, Hua D, Bolstad PV, Birdsey R, Mladenoff DJ. 2011. The effects of forest harvest intensity in combination with wind disturbance on carbon dynamics in a Lake States mesic landscape. Ecological Modelling 222: 144-153.

Scheller RM, Kretchun A, Hawbaker TJ, Henne PD. 2019. A landscape model of variable social-ecological fire regimes. Ecological Modelling 401: 85-93.

Soil Survey Staff, Natural Resources Conservation Service, United States Department of Agriculture. Web Soil Survey. Available online at https://websoilsurvey.nrcs.usda.gov/.

Yarnell SL. 1998. The Southern Appalachians: A History of the Landscape. General Technical Report SRS-18. Ashville, NC: U.S. Department of Agriculture, Forest Service, Southern Research Station. 52 p.
