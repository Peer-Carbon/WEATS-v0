<!--

Specific focus of this methodology:
- Constant energy use within a specified time window (i.e. not accounting for energy savings)
- Submetered demand of the flexible assets
- Baseline = representative history OR controller baseline schedule


This method does NOT cover:
- Impact from changes on the production side due to grid control room or market decisions (dispatch)
- Interventions providing a combination of energy savings and flexibility

We would like to allow covering:
- Co-optimisation
- Shorter data histories (where realistic)

Inspirations:
- https://flexvalue.readthedocs.io/en/latest/ 

--> 
# Carbon-flexing of demand

**Name**: *Carbon-flexing of demand*

**Developed by**: *[PeerCo](www.peerco.earth)*

**Revision date**: *November 7th 2024*

**Sectoral scope**:  *Energy / Energy Distribution / Energy Demand*


## Summary description

This methodology focuses on measurements and verification of the impact of delivering flexibility from residential heating systems on a given site, where this flexibility is operated according to a carbon-intensity signal.
The purpose of this methodology is to generate *Environmental Attribute Certificates* representing the value of energy flexibility delivered (at a specific time and geographical location), which can then be used in reporting or traded.

## Definitions

This section provides definitions of the key aspects of this methodology.

### Normative language

The following terminology is used throughout this document to outline requirements and guidelines (accordingly with common standardisation practices):
- **shall** indicates a *requirement*,
- **should** indicates a *recommendation*,
- **may** indicates an *option* that is permitted.

### Acronyms


| Acronym | Full text           |
|---------|---------------------|
| CDM     | Clean development mechanism |
| EAC     | Energy Attribute Certificate |
| GHG     | Greenhouse gas(es)  |
| kW      | Kilowatt (power unit) |
| kWh     | Kilowatt-hour (energy unit) |
| UN      | United Nations      |

### Glossary

The following definitions shall apply to all usages of the following terms (including their plural forms) in this methodology:

- **Baseline** refers to a counterfactual situation where the change (delivery of flexibility in the context of this methodology) did not happen.

- **Digital certificate** is a generic term designating environmental attributes in digital form generated using this methodology, which will correspond to Energy Attribute Certificates (EACs).

- **Emission intensity** (or *carbon intensity*) is a measure of how clean grid electricity is. It refers to how many grams of carbon dioxide equivalent (gCO2e) are released to produce a kilowatt hour (kWh) of electricity. In this methodology, an *average* measure of this factor *on the demand side* is considered at every hour and for a given grid area, meaning that this number reflects the carbon intensity of the *average kilowatt-hour consumed* in this given hour and grid region.

- **Flexibility** designates the usage of the ability of an energy-consuming asset to adjust its demand compared to a *baseline* demand profile.

- **Flexible asset** designates the energy-consuming asset (or set of assets) whose operation is modified to provide the flexibility.

- **High resolution data** is data whose time resolution is hourly or sub-hourly (e.g. every 15 or 30 minutes).

- **Grid region** is a generic term used here to refer to a specific sub-division of a large-scale power system. This may be a balancing region, a country-wide grid, a market-bidding region depending on the local context. The spatial resolution used for the grid region used in a given application should be as granular as allowed by the data available.

- **Site** is a geographically delimited area where the flexible assets are installed.

## Applicability conditions

This section lays out the requirements on a given context for this methodology to be applicable.

### System eligibility requirements

The system to which the methodology is applied shall meet the following requirements to be eligible:


1. dedicated sub-metering of the power delivered to the *flexible assets* is implemented, either individually or aggregated (if several flexible assets are present on site),

<!-- Here, we might want to allow for flexibility in potential other subsystems covered by the same meter (e.g. these shall not use more than 5% of the energy used by the asset) -->

2. there is no on-site generation whose output is affected by the delivery of flexibility,

3. the control delivering flexibility does not aim at decreasing (or increasing) the energy demand, but only focuses on shifting a given demand in time,
<!-- This is to ensure that we can claim that before/after energy usage is the same -->

4. baseline is available in the form of either:

    a. an original schedule transmitted by the control

    or

    b. historical high resolution data covering a representative period where the system was operating in a *business-as-usual* manner.
    <!-- We need to define what a "representative period" looks like -->



### Requirements on the system during the project lifetime

During the whole duration of the project, the *flexible assets* owner shall demonstrate proof of ownership of these assets and continued operation of their heat delivery. This documentation shall be made via all of the following:

- sharing of consumption data throughout the period,

- in the case of usage of the environmental attribute in reporting:
    - contractual renunciation to the possibility of transfer of the environmental assets to a third party.

- in the case of sales of the environmental attribute to a third party:
    - contractual transfer of the environmental attribute ownership of the self-consumed generation,
    - carbon accounting for the site (location and market-based), if carried out, should reflect the sale of the carbon reduction corresponding to the transfer of the certificate.


### Requirements on the operating context

The power system within which the system operates shall meet the following requirements to be eligible:

1. Hourly (or sub-hourly) carbon intensity data is available. Forecasts generated by the system operator may be used where reconciled actual data is not available, on the condition that only latest available forecast for each point in time is used as a "best in class" approximation to the actual carbon intensity. <!-- This is to allow us to use the local carbon intensity in the UK -->

<!-- We may want to have some sort of criterion about a minimum amount of fluctuations of the carbon intensity over time. This will however need to be specified in such a way that it does not excessively complexify applicability -->
[...]


## Project boundary

[...]

## Measurement

This section introduces the underlying data requirements.

### Asset data

<!-- To be written -->

### Emission intensity data

The emission intensity data used in calculations shall meet the following requirements:

1. the time resolution of the data is hourly or more granular,
2. the geographical resolution of the data is country-level or more granular,
3. the signal corresponds to an average emission intensity of *consumed* electricity,
4. the source of the carbon intensity data shall be recorded as part of the digital asset generated.

Data may originate from one of the sources listed in *Appendix 1*.

## Verification and additionality

This section provides the key aspects of the verification methodology, based upon the data of the previous section.

### Baseline scenario

The baseline scenario considered is a scenario where the flexibility is not delivered an the flexible asset. Two methods are allowed, as described in the sub-sections below. The method chosen shall be specified in the digital asset.

#### Method 1 - Using a historical counterfactual

(...)


#### Method 2 - Using an original schedule counterfactual

(... CR method ...)



### Quantification of GHG emission reduction and associated trading requirements

For each period *i*, the certificate's energy content shall be:
> EAC energy content[i] [kWh] = (Actual energy demand[i] [kWh]) - (Baseline energy demand[i] [kWh])

and its carbon content shall be:
> EAC carbon content[i] [gCO2e] = (EAC energy content[i] [kWh]) x (Average grid emission intensity[i] [gCO2e/kWh])

This will naturally lead to a combination of EACs with positive and negative values. In order to ensure meaningful usage of the EAC scheme, trading of such EACs shall only be permitted in bulks where the sum of the energy content of the EACs in a bulk shall be below a near-zero threshold in absolute value. For practical purposes and to account for rounding errors in the computation process, "near-zero" shall be interpreted as a number below 0.1% of the sum of positive EACs in the bulk:

> $EAC \  bulk \  energy \  content \ threshold \ [kWh] = \frac{\sum_i max(0, EAC \ energy \ content \ [i] \ [kWh])}{1000}$

<!-- This provision is to avoid the risk of trading only the positive part and having liabilities stacking up on the other end -->

### Information content of the digital certificate

The following conventions shall apply to the information provided:
- timestamps are given in UTC timezone
- dates are given in the local timezone where the asset is located
- "period" refers to the specific time range with explicit start (inclusive) and end (exclusive) where the corresponding amount of energy was generated
- energy amounts are expressed in Wh

The digital certificates resulting from this verification methodology shall contain the following information:

- Flexible asset informations:
    - Name of the device
    - A unique identifier
    - Address of the site where it is installed (optional if GPS coordinates are provided)
    - GPS coordinates of the site (optional if full address is provided, as it will be inferred from it)
    - Rated power (kWp)
    - Date when the flexibility delivery started

- Grid connection information for the site:
    - Grid region type (e.g. "market-bidding zone")
    - Identifier of the grid region (e.g. "UK")
    - Identification of the grid connection (such as power meter number), where this identifier should correspond to the standard identification for the country/zone of application when such a standard exists (e.g. MPAN meter numbers in the United Kingdom).

- Time information about the period:
    - Start timestamp
    - End timestamp

- Energy content:
    <!-- Here we need to find what information is the relevant information -->

- Emission intensity of the grid:
    - Average emission intensity of the grid over the period
    - Source of the average emission intensity data (e.g. "carbonintensity.org.uk")
    - Identifier of the grid region corresponding to the emission intensity data (e.g. "London")

- Details about certificate issuance:
    - Timestamp when the certificate was generated
    - Country for which the certificate is issued
    - A link to this methodology (where the URL points to the specific version used to generate the certificate)

- Legal information:
    - Reference to the contractual proof of ownership of the environmental attributes generated by the heating asset.


## References

*(None)*

<!-- 
Wanted to use:
-  FlexValue ( https://flexvalue.readthedocs.io/en/latest/ ) but it's inadequate because it uses static datasets.
- OpenEEmeter : has an hourly data approach ( https://eemeter.openee.io/tutorial.html#caltrack-hourly-quickstart ) but all is being rewritten at the moment for the hourly part 
- 5-in-10 approach from CAISO : ( https://bpmcm.caiso.com/BPM%20Document%20Library/Demand%20Response/BPM_for_Demand_Response_V5_clean.pdf#page=35 ) the method is ill-suited as it's looking at a reduction
-->

---

# Appendix

Contextual information is provided in the appendices below. These only contain informational elements which do not hold normative value.

## Appendix 1 - potential sources of emission intensity data

The emission intensity data used in calculations shall originate from the source in the table below for the geography corresponding to the location of the assets.

| Geography     | Emission intensity source                              |
|---------------|--------------------------------------------------------|
| Great Britain | [National Grid ESO's *carbonintensity.org.uk* API](https://www.carbonintensity.org.uk/) |
| Global        | [ElectricityMaps API](https://www.electricitymaps.com/) |

The source of the carbon intensity data shall be recorded as part of the digital asset generated.

## Appendix 2 - M&V plan template

(reuse and adapt from solar methodology where available)

[...]