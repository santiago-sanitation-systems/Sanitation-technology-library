# Santiago Sanitation Technology Library

The Santiago Sanitation Technology Library characterizes sanitation technologies in a format that can be used directly with
[Santiago](https://github.com/santiago-sanitation-systems/Santiago.jl).

## Files
This repository contains the latest version of the technology library, a template for an input case file and a default input masses file as they are used in [_Santiago_](https://github.com/santiago-sanitation-systems/Santiago.jl/tree/a77dec97b3048b53c09a33de8aea7e165f60ef65). Refer to the _Santiago Wiki_ for more information about the files and how to use them. The documentation contains the background information about the functionalities of calculations in _Santiago_ or further information about appropriateness attributes and their calculation. 
The folder "graphics" contains graphics as they are used in the _Santiago Wiki_ and can therefore be neglected.

## Download

The _latest_ version of the technology file can be downloaded from Julia
with
```Julia
url = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/technology_library.json"
download(url, "technology_library.json")
```

The input case template can be downloaded with the following code:
```Julia
url_1 = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/case_input.json"
download(url_1, "input/case_input_template.json")
```
The default input masses file is downloaded and converted as follows:
```Julia
# Download the default input masses file

    url_2 = "https://raw.githubusercontent.com/santiago-sanitation-systems/Sanitation-technology-library/master/default_input_masses.json"
    download(url_2, "input/default_input_masses.json")

# read in default_input_masses

    _input_masses = open("input/default_input_masses.json","r") do f
        JSON3.read(f)
    end
# convert to type 'Dict{String,Dict{String,Real}}'
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

