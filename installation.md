# Installation and requirements
`PQPolygonSDK.jl` requires the [Julia](https://julialang.org/downloads/) programing language and a [Polygon.io API key](https://polygon.io) to access financial data. 


`PQPolygonSDK.jl` can be installed, updated, or removed using the [Julia package management system](https://docs.julialang.org/en/v1/stdlib/Pkg/). To access the package management interface, open the [Julia REPL](https://docs.julialang.org/en/v1/stdlib/REPL/), and start the package mode by pressing `]`.
While in package mode, to install `PQPolygonSDK.jl`, issue the command:
```julia       
(@v1.7.x) pkg> add PQPolygonSDK
```
Once installed, to use `PQPolygonSDK.jl` in your projects (like a Pluto notebook), issue the command:
```julia
julia> using PQPolygonSDK
```