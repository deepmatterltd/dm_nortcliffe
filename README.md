# dm_nortcliffe

This repo contains recipe and runtime data for the paper "Data led synthesis: an inquiry based-learning project in reaction optimization with DigitalGlassware®", Nortcliffe et al, 2022.

All data was captured by [Deepmatter's DigitalGlassware®](https://deepmatter.io/) platform.

# Data

## Mappings

See the document `run_mappings.csv` in the root directory of this repo as a map of which groups performed each run.

### Sensor Data

Each PCRR document embeds all sensor data associated with a run. Information on mapping DeviceX's sensor names to human-readable equivalents can be found in the `devicex_mappings.csv` document. As a simple rule, any sensor ending with "I", "E", or "A" corresponds to the sensor being below the meniscus (_immersed_), above the fill level (_exposed_) or in the handle of DeviceX (_ambient_). All sensor data collected has been reported, but only some represent high level sensors user will be familiar with (e.e. temperature of solution). The CSV indicates which are these "primary" sensors.

## PCML

The Practical Chemistry Markup Language (PCML) is an XML document which represents the chemical recipe which a user has developed in DigitalGlassware®. It contains all chemicals,
operations and metadata associated with a recipe *prior* to execution.

See the `pcml` directory for all recipes generated during the project, where each filename is the associated run ID. Note that there will be duplicates of recipes here, such as 
the same recipe for the first phase of work all being taken from the same root recipe. This structure has been used for convenience of mapping to the various run records 
encoded in the PCRR.

## PCRR

The Practical Chemistry Runtime Records (PCRR) is another XML document which contains all data associated with a chemistry experiement, during and after it has been executed. All 
aspects of the executed run are embedded (including the original PCML associated with the recipe), the start and end time of each executed operation, final run purities and yields
(if relevant), all sensor data from connected devices, and other metadata.

See the `pcrr` directory for the 23 individual runs performed, where filename is the run record ID.
