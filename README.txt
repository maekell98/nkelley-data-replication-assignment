OVERVIEW
This dataset presents data on three roosting structure of three species of flying-fox at eight sites in south-east Queensland and north-east New South Wales,Australia. 
Species included the grey-headed flying-fox (P. poliocephalus), black flying-fox (Pteropus alecto) and little red flying-fox (Pteropus scapulatus). 
All sites were previously documented as having a continuous population of grey-headed or black flying-foxes. 
Little red flying-foxes visited some roost sites intermittently, however no roost sites occurred within the distribution of spectacled flying-foxes.


RAW
We mapped the spatial arrangement of all overstory, canopy and midstory trees in a grid network of 10 stratified random subplots (20 x 20 meters each) per roost site. 
Subplots were stratified throughout perceived “core” (five subplots) and “peripheral” (five subplots) roosting areas, classed as areas observed to be frequently occupied (core) or infrequently (peripheral) by bats (Welbergen 2005). 
Core and peripheral areas were evaluated from regular observations made prior to roost tree mapping, though note that these categories were revised subsequently with the quantitative data. 
Trees were mapped and tagged using tree survey methods described in the “Ausplots Forest Monitoring Network, Large Tree Survey Protocol” (https://doi.org/10.1371/journal.pone.0137811).

To evaluate spatio-temporal patterns in flying-fox roosting, we revisited all tagged trees and scored the extent of species occupancy using the following tree abundance index: 0= zero bats; 1= 1-5 bats; 2=6-10 bats; 3=11-20 bats; 4=21-50 bats; 5=51-100 bats, 6=101-200 bats, 7= >200 bats. 
For a subset of trees (N=60 per site, consistent through time) absolute counts and minimum/maximum roosting heights of each species were taken. 
Overall roost perimeter (perimeter of area occupied) was mapped with GPS (accurate to 10 meters) immediately after the tree survey to estimate perimeter length and roost area. 
Total abundance at each roost was also estimated with a census count of bats where feasible (i.e., where total abundance was predicted to be <5,000 individuals), or by counting bats as they emerged in the evening from their roosts (“fly-out”), as per recommendations in Westcott et al. (2011). If these counts could not be conducted, population counts from local councils (conducted within ~a week of the bat surveys) were used, as the total abundance of roosts is generally stable over short timeframes (Nelson 1965b). 
Because roost estimates become more unreliable with increasing total abundance, and because our estimation methods were intrinsically linked with total abundance, we converted the total estimated abundance into an index estimate (where bin ranges increase with total abundance) for use in analyses, as per values used by the National Flying-Fox Monitoring Program (2017). Index categories were as follows: 1: 1-499 bats; 2: 500-2,499 bats; 3: 2,500-4,999 bats; 4: 5,000-9,999 bats; 5: 10,000-15,999 bats; 6: 16,000-49,999 bats; and 7: 50,000+ bats.
Roosting surveys were repeated once a month for 13 months (August 2018 - August 2019).
Methodological details are described in detail in the published paper 'Conventional wisdom on roosting behaviour of Australian flying foxes – a critical review, and evaluation using new data' (DOI https://doi.org/10.1002/ece3.8079). Raw data are available from this Dryad Dataset (https://doi.org/10.5061/dryad.g4f4qrfqv)


PROCESSED DATA

Information collected during the bat roosting surveys were used to calculate measures of bat density and abundance at three scales: roost-level, subplot-level and tree-level. For a visual summary of metrics see Figure 2 in the published paper ('Counterintuitive scaling between population abundance and local density: implications for modelling transmission of infectious diseases in bat populations'). Note that where index abundance scores were used in calculations, the middle value of the index range was taken. 

Roost-level density was calculated by dividing the total roost index abundance score by the total roost area (Figure 2A). Measures of subplot-level density were estimated with two methods: either as the tally of tree-level index abundance scores per subplot divided by subplot area (“subplot-level density”,  Figure 2B), or as the average of fixed-bandwidth weighted kernel estimates, estimated using the spatstat package in R (Diggle 1985) (“subplot-level kernel density”, Figure 2C). Kernel estimates are spatially explicit and give the density of a spatial pattern, estimated per pixel over a smoothed area (Baddeley 2010). Kernels were estimated from the spatial location of trees weighted by tree-level index abundance scores, with Gaussian kernel smoothing and a smoothing bandwidth of 0.6. Bandwidth was selected by comparing projected kernel density values to expected density values based on tree abundance and canopy area. Kernel averages were then calculated per subplot. To prevent dilution of the density estimates with unoccupied space, we included only occupied pixels in the subplot average (pixel size = 0.156 x 0.156 meters). This latter approach has the advantage of explicitly incorporating the spatial distribution of bats into the density estimate, and therefore gives a better representation of aggregations in occupied space. Note that neither roost nor subplot-based density measures consider the vertical distribution of bats.

Measures of tree-level density were estimated in either two-dimension (2-D; for comparison with other two-dimensional estimates) or three-dimension (3-D). Tree-level 2-D density was estimated from tree-level index abundance scores and canopy area (Figure 2D). Tree-level 3-D density was estimated for the tree subset, as the absolute count of bats divided by the volume of tree space occupied (i.e. per cubic metre rather than square metre, Figure 2E). Volume of tree space was calculated from the height range occupied (maximum height minus minimum height) and the approximate crown area of trees. To estimate crown area of tagged trees for both measures, we computed the area of Dirichlet-Voronoi tessellations from tree distribution maps of canopy trees per subplot, with the spatstat package in R (Baddeley 2010). To control for edge effects, and to prevent overestimation of crown area for overstory trees and trees outside of the canopy, we imposed a maximum crown area of 199 m2 (radius ~8 m). This value was selected based on mean values reported across species of eucalypts in New South Wales (Verma et al. 2014), eucalypts being broadly representative of trees in these roost sites (Brooks 2020). In total, 218 of the 2,522 tagged trees (8%) were imposed with the maximum crown area value. Crown area of midstory trees was assigned as the first quartile of canopy tree crown area (5.8 m2), to reflect observations that trees beneath the canopy were typically smaller than trees within the canopy. Mean calculated crown area was 30.4 m2 (crown radius ~ 3.1 m). To investigate whether the choice of maximum crown area impacted results, we also repeated analyses for additional values of maximum crown area (140 m2, 170 m2 and 230 m2) chosen to cover the range in smallest to largest mean values reported for individual eucalypt species in Verma et al. (2014).

The data provided here are the processed density and abundance values (response/dependent variables), and roost features (predictor/independent variables) calculated from raw data, used in the manuscript 'Counterintuitive scaling between population abundance and local density: implications for modelling transmission of infectious diseases in bat populations'

The file provided (merged.data.csv) contains all levels of data (roost-level, subplot-level, tree-level). Rows are individual trees (tree.accession) measured per site*month (site.accession). Individual trees per site*month are replicated for each species roosting in the tree (species - BFF = black flying-fox, GHFF = grey-headed flying-fox, LRFF = little red flying-fox, all=all species combined). Data from higher nested levels (e.g. roost-level) are replicated for each lower nested level (e.g. tree-level). 

Data are: 
- site.code - the roost (DAVO=Avondale, DBUR=Burleigh, DCAN=Canungra, DCLU=Clunes, DLIS=Lismore, DRED=Redcliffe, DSUN=Sunnybank, DTOW=Toowoomba)
- session - session number (1=August 2018, 2=September 2018, 3=October 2018, and so on)
- site.accession - the unique roost*session ID number (DAVO=Avondale, DBUR=Burleigh, DCAN=Canungra, DCLU=Clunes, DLIS=Lismore, DRED=Redcliffe, DSUN=Sunnybank, DTOW=Toowoomba)
- subplot - the subplot number (1-10)
- rep - unique site.accession*subplot ID number
- species - BFF=black flying-fox, GHFF=grey-headed flying-fox, LRFF=little red flying-fox
- Plot.Abundance - total subplot abundance estimated from index abundance values (recorded for all trees) [subplot-level predictor/independent variable]
- density - subplot density estimated from total subplot abundance (above) divided by subplot area [“subplot-level density”]
- Plot.Available.Trees - the number of midstory, canopy and overstory trees per subplot
- Plot.Prop.Trees.Occupied - the proportion of trees occupied per subplot [subplot-level predictor/independent variable]
- Plot.Kernel.Density - the kernel density estimate of bats per subplot [“subplot-level kernel density”]. Estimated with zero kernel values (i.e. blank space) removed
- Ntrees - total number of tagged trees in subplot
- a.can - number of tagged trees within subplot with tallest height above the canopy
- b.can - number of tagged trees within subplot with tallest height below the canopy
- can - number of tagged trees within subplot with tallest height at the canopy
- E-OG - tally of crown classes within subplot, of tagged trees (D=dominant, C=co-dominant, I=intermediate, CI=co-dominant but below canopy, S=suppressed, E=emergent, OG=open)
- roost.type - urban (if within the limits of a major urban area) or rural (if outside the limits of a major urban area) - see map figure in manuscript
- core.periph - whether subplot was occupied >80% of surveys where bats were present at the roost (core) or <80% (peripheral) - see definition and justification in manuscript 
- NN.distance - the average distance between trees per subplot (i.e. nearest neighbors)
- plotID- unique site*subplot ID number
- Roost.Area - the total area (meters squared) of the roost per roost, calculated from the roost perimeter [roost-level predictor/independent variable]
- roost.perimeter- the total perimeter (meters of the roost per roost, calculated from the roost perimeter 
- Roost.Available.Trees - a count of all tagged midstory, canopy and overstory trees within the roost
- Roost.Index.Abundance - an estimate of roost abundance per roost. Index categories were as follows: 1 = 1-499 bats; 2 = 500-2,499 bats; 3 = 2,500 - 4,999 bats; 4 = 5,000 - 9,999 bats; 5 = 10,000 - 15,999 bats; 6 = 16,000 - 49,999 bats; and 7 = > 50,000 bat [roost-level predictor/independent variable]
- Roost.Abundance - the abundance estimate of the roost per roost, estimated from direct census counts or taken from council estimates 
- tree.accession - unique tree ID. Name is structured as DAVO(site) 01(plot number) 001(tree number)
- Tree.Abundance.all - an estimate of abundance per tree, from index abundance values for all trees [response/dependent variable: 'tree-level abundance']
- Tree.Preference.all - indicates tree preference for roosting: whether a tree is occupied =>80% of surveys (core trees=1) or less (peripheral trees=0) per tree [tree-level predictor/independent variable]
- Tree.Occupancy.all - indicates tree preference for roosting: is the proportion of times a tree is occupied across the survey per tree. This is calculated for surveys when bats are present, only
- Tree.Abundance.subset - a direct count of abundance per tree, from a subset of trees (N=6 per plot + zero values)
- max - maximum roosting height of bat species (meters), measured for a subset of trees only
- min - minimum roosting height of bat species (meters), measured for a subset of trees only
- Tree.Height.Range.subset - the difference between the highest and lowest bat per tree, taken for a subset of trees only
- value_dirichlet - the calculated crown area (meters squared)
- Tree.Density.subset - the density of bats per tree, estimated as the total count by the height range and crown area, for a subset of trees only [response/dependent variable: 'tree-level 3-D density']
- Plot.Density.Trees - the density of midstory, canopy and overstory trees per subplot [subplot-level predictor/independent variable]
- Roost.Density.Trees - the density of tagged midstory, canopy and overstory trees per roost [roost-level predictor/independent variable]
