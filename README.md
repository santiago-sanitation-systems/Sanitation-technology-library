# Santiago Sanitation Technology Library

The Santiago Sanitation Technology Library characterizes sanitation technologies in a format that can be used directly with
[Santiago](https://github.com/santiago-sanitation-systems/Santiago.jl).
The methodology to establish this library and all data including literature references and assumptions are compiled in the [Sanitation Technology Library documentation](Spuhler_et_al_2023_SANTIAGO_Documentation_and_technology_data_library.pdf).

## Citation
Spuhler, D. Scheidegger, A., Roller, L., Fritzsche, J., Willimann, C., Ilmanen, K. (2022) SANTIAGO documentation and technology library: functionalities, definitions and data for appropriateness profiles and transfer coefficients. Continuously updated URL: https://github.com/SANTIAGO-sanitation-systems/Sanitation-technology-library

## Folders and files
This repository contains :
-  A folder _Documentation_ that contains the _Santiago Sanitation Technology Library Documentation_. The documentation contains:
-- Part A: documents the functionalities and the definitions underlying [_Santiago_](https://github.com/santiago-sanitation-systems/Santiago.jl/tree/a77dec97b3048b53c09a33de8aea7e165f60ef65)
-- Part B: provides a data sheet for all currently implemented technologies presenting all original data used to describe the technology for [_Santiago_](https://github.com/santiago-sanitation-systems/Santiago.jl/tree/a77dec97b3048b53c09a33de8aea7e165f60ef65) as well as literature references and assumptions.
-  A folder _latest_full_example_input_files_ with the latest version of the technology library in the json format and addtional files required by [_Santiago_](https://github.com/santiago-sanitation-systems/Santiago.jl/tree/a77dec97b3048b53c09a33de8aea7e165f60ef65). Refer to the _Santiago Wiki_ for more information about the files and how to use them.
- A folder _bestpractice_example_input_files_ with a realistic but reduced example of the technology library and additional input files for [_Santiago_](https://github.com/santiago-sanitation-systems/Santiago.jl/tree/a77dec97b3048b53c09a33de8aea7e165f60ef65). This is the standard example used by the example documented in the [_Santiago Wiki_](https://github.com/santiago-sanitation-systems/Santiago.jl/wiki).
- The folder _Graphics_ contains graphics as they are used in the _Santiago Wiki_ and can therefore be neglected.

## Download for usage with Santiago

The _latest_ version of the technology library can be downloaded from Julia with
```Julia
date = Dates.today()
    url = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/latest_full_example_input_files       /latest_full_technology_library.json"
    download(url, "input/latest_full_technology_library_$date.json") 
 ```
The _additional_ files can be downloaded from Julia with 
```Julia
# example case
    url = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/latest_full_example_input_files/latest_full_case_input.json"
    download(url, "input/latest_full_case_input_$date.json")

# example inflow masses for user interfaces
    url = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/latest_full_example_input_files/latest_full_inflow_masses.json"
    download(url, "input/latest_full_inflow_masses_$date.json")

# the inflow masses have to be converted to type 'Dict{String,Dict{String,Real}}'
    input_inflow_file = "input/latest_full_inflow_masses_$date.json"
    _input_masses = open(input_inflow_file,"r") do f  
        JSON3.read(f)
    end
    input_masses = Dict(String(k1) => Dict(String(k2) => v2 for (k2, v2) in v1)
                     for (k1,v1) in _input_masses)
    end
```

## References

Spuhler, D., Scheidegger, A. and Maurer, M.  2018.  Generation of sanitation system options for urban planning considering novel technologies. Water Research 145, 259-278. DOI: 10.1016/j.watres.2018.08.021.

Spuhler, D., Germann, V., Kassa, K., Ketema, A.A., Sherpa, A.M., Sherpa, M.G., Maurer, M., Lüthi, C. and Langergraber, G.  2020.  Developing sanitation planning options: a tool for systematic consideration of novel technologies and systems. Journal of Environmental Management 271. DOI: 10.1016/j.jenvman.2020.111004.

[dataset] Spuhler, D. and Roller, L. 2020  Sanitation technology library: details and data sources for appropriateness profiles and transfer coefficients. Supplementary material for: Spuhler et al 2020 Ex-ante quantification of nutrient, total solids, and water flows in sanitation systems. DOI: 10.25678/0000ss.

Spuhler, D., Scheidegger, A. and Maurer, M.  2020.  Ex-ante quantification of nutrient, total solids, and water flows in sanitation systems. Journal of Environmental Management, 111785. DOI: 10.1016/j.jenvman.2020.111785.

Spuhler, D., Scheidegger, A. and Maurer, M.  2020.  Comparative analysis of sanitation systems for resource recovery: influence of configurations and single technology components. Water Research 186, 116281. DOI: 10.1016/j.watres.2020.116281.

