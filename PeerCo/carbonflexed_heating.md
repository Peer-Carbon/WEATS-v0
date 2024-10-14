<!--

This is a template to be used for methodology development. The content of this file shall follow the Markdown conventions with Github flavour.


If you need help on the Markdown syntax for Github, here is a good link:
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

And if you need a tool to make the rendering work in VSCode, here is a good plugin:
https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles 

--> 
# Carbon-flexing of space and water heating

**Name**: *Carbon-flexing of space and water heating*

**Developed by**: *[PeerCo](www.peerco.earth)*

**Revision date**: *October 10th 2024*

**Sectoral scope**:  *Energy / Energy Distribution / Energy Demand*


## Summary description

This methodology focuses on measurements and verification of the impact of delivering flexibility from residential heating systems on a given site, where this flexibility is operated according to a carbon-intensity signal.
The purpose of this methodology is to generate *Environmental Attribute Certificates* representing the energy flexibility delivered (at a specific time and geographical location), which can then be used in reporting or traded.

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

The following definitions apply to all usages of the following terms (including their plural forms) in this methodology:

- **Digital certificate** is a generic term designating environmental attributes in digital form generated using this methodology, which will correspond to Energy Attribute Certificates (EACs).

- **Emission intensity** (or *carbon intensity*) is a measure of how clean grid electricity is. It refers to how many grams of carbon dioxide equivalent (gCO2e) are released to produce a kilowatt hour (kWh) of electricity. In this methodology, an *average* measure of this factor *on the demand side* is considered at every hour and for a given grid area, meaning that this number reflects the carbon intensity of the *average kilowatt-hour consumed* in this given hour and grid region.

- **Heating asset** designates the system delivering heating, either as *Space-heating asset* or *Water-heating asset*.

- **High resolution data** is data whose time resolution is hourly or sub-hourly (e.g. every 15 or 30 minutes).

- **Grid region** is a generic term used here to refer to a specific sub-division of a large-scale power system. This may be a balancing region, a country-wide grid, a market-bidding region depending on the local context. The spatial resolution used for the grid region used in a given application should be as granular as allowed by the data available.

- **Space-heating asset** is a heating system (e.g. radiator, heat-pump, ...) delivering heating of space.

- **Target building zones** is the set of the parts of the building to which the heating is delivered.

- **Water-heating asset** is a system delivering hot water (e.g. water boiler).


## Applicability conditions

This section lays out the requirements on a given context for this methodology to be applicable.

### System eligibility requirements

The system to which the methodology is applied shall meet the following requirements to be eligible:


1. the *heating assets* are powered by electricity only, 

2. the heating of the *target building zones* is exclusively provided by the *heating assets*,

3. dedicated sub-metering of the power delivered to the *heating assets* is implemented, either individually or aggregated at building level,

4. [...]

### Requirements on the system during the project lifetime

During the whole duration of the project, the *heating assets* owner shall demonstrate proof of ownership of these assets and continued operation of their heat delivery. This documentation shall be made via all of the following:

- sharing of consumption data throughout the period,

- in the case of usage of the environmental attribute in reporting:
    - contractual renunciation to the possibility of transfer of the environmental assets to a third party.

- in the case of sales of the environmental attribute to a third party:
    - contractual transfer of the environmental attribute ownership of the self-consumed generation,
    - carbon accounting for the site (location and market-based), if carried out, should reflect the sale of the carbon reduction corresponding to the transfer of the certificate.


### Requirements on the operating context

The project country shall meet the following criteria:
1. delivery of micro-solar is not a requirement for building development or to meet an enforced carbon quota,
2. emission intensity data is available at the hourly (or sub-hourly) level for the national or local grid.


## Project boundary

GHG sources included or excluded from the project boundary.

| Source                     | Gas     | Included | Justification           |
| -------------------------- |---------|----------|------------------------ |
| Grid electricity displaced | $CO_2$  | Yes      | Main emission source    |
| Grid electricity displaced | $NO_x$, $SO_x$  | No       | Emissions data is not sufficiently granular and available the half hour or hour |


## Measurement

This section introduces the underlying data requirements.

### Asset data

PV production data shall be acquired via automatic digital communication to PeerCo's cloud once the project is established. However, in the initial phase of setting up a project (qualifying the site, its data and quantifying the benefits of the scheme), offline extractions of the data in an open format (which may be CSV, XLSX, etc.) may be accepted.

All self-consumption data (and related generation data) shall be quality controlled prior its usage to generate verified certificates. This verification shall include:
1. the maximum PV generation is in line with the PV asset's nominal rating,
2. self-consumption is always lower than the total consumption,
3. no significant PV generation is happening when there is no solar irradiance (e.g. at night).

Where data is missing, data filling (e.g. with interpolation) shall not be carried out. Digital certificates shall therefore be generated based upon measured data only.

When carrying out this asset data verification, a tolerance should be given for numerical purposes (e.g. to account for rounding of measurements by digital systems). This tolerance shall however not be of a magnitude that significantly impacts the volume of the certificates generated.

### Emission intensity data

The emission intensity data used in calculations shall meet the following requirements:

1. the time resolution of the data is hourly or higher,
2. the geographical resolution of the data is country-level or higher,
3. the signal corresponds to an average emission intensity of *consumed* electricity,
4. the source of the carbon intensity data shall be recorded as part of the digital asset generated.

Data may originate from one of the sources listed in *Appendix 2*.

## Verification and additionality

This section provides the key aspects of the verification methodology, based upon the data of the previous section.

### Baseline scenario

The baseline scenario considered is a scenario where the PV asset is not installed, therefore zero generation happens from this asset and electricity is imported from the grid instead.

### Quantification of GHG emission reduction and/or clean energy produced

This methodology supports the generation of EACs accounting for the energy consumed on site, which also account for the avoided carbon emissions (as an extra information embedded in the certificates).

The clean energy generation accounted in this methodology shall be limited to the self-consumed part of the PV asset (i.e. exports are thereby excluded, as they may already be accounted for in another certificate scheme).

Certificates shall be generated for specific time periods, where the length of these time periods shall not exceed one hour. In contexts where the electricity market's settlement period is less than an hour (e.g. 30 minutes for Great Britain), the certificates may be issued for durations matching this settlement period.

For each period *i*, the certificate's energy content shall be:
> EAC energy content[i] [kWh] = Self-consumed PV asset generation[i] [kWh]

and its carbon content shall be:
> EAC carbon content[i] [gCO2e] = (Self-consumed PV asset generation[i] [kWh]) x (Average grid emission intensity[i] [gCO2e/kWh])


### Information content of the digital certificate

The following conventions shall apply to the information provided:
- timestamps are given in UTC timezone
- dates are given in the local timezone where the asset is located
- "period" refers to the specific time range with explicit start (inclusive) and end (exclusive) where the corresponding amount of energy was generated
- energy amounts are expressed in Wh

The digital certificates resulting from this verification methodology shall contain the following information:

- PV asset informations:
    - Name of the production device
    - A unique identifier
    - Address of the site where it is installed (optional if GPS coordinates are provided)
    - GPS coordinates of the installation (optional if full address is provided, as it will be inferred from it)
    - Rated power (kWp)
    - Date when the PV panel started generating power on the site

- Grid connection information for the site:
    - Grid region type (e.g. "market-bidding zone")
    - Identifier of the grid region (e.g. "UK")
    - Identification of the grid connection (such as power meter number), where this identifier should correspond to the standard identification for the country/zone of application when such a standard exists (e.g. MPAN meter numbers in the United Kingdom).

- Time information about the period:
    - Start timestamp
    - End timestamp

- Energy content:
    - Amount of PV generation from the asset that was self-consumed over the period (in Wh)

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