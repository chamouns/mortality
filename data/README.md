# Vaccine hesitancy data
See [this story from the CDC](https://data.cdc.gov/stories/s/Vaccine-Hesitancy-for-COVID-19/cnd2-a6zw).
Contains PUMA-level estimation for vaccine hesitancy, along with county-level information of other data.

# Census API information

We use the [tidycensus](https://walker-data.com/tidycensus/index.html) package to obtain the data.
Install it using `install.packages("tidycensus")`.

See the file `census.R` for some ideas.

Use `geography="zcta"` with `get_acs()` or `get_decennial()` to get results by ZIP code.

We also use [censusapi](https://www.hrecht.com/censusapi/). See the file `census.R` for some examples.

### Some things to note
* `acs/acs1` has data only for areas with population 65,000+. See [here](https://www.census.gov/programs-surveys/acs/geography-acs/areas-published.html) for the precises numbers.
* `acs` doesn't seem to do ZIP codes, while `dec` does. We should think about how to join the data.
* See the [Geography reference files](https://www.census.gov/geographies/reference-files.2020.html) for more info on geographies. Relationship files can be used to map e.g. counties to ZIP codes, and gazetteer files give information on the area, e.g. land surface area.