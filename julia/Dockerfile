FROM julia:latest

RUN julia -e 'using Pkg; Pkg.activate("."); Pkg.instantiate(); Pkg.add("VCFTools"); Pkg.add("DataFrames"); Pkg.add("ArgParse")'

CMD ["/bin/bash"]
