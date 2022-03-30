# Models and methods

## Build a user model
All [Polygon.io](https://polygon.io) application programming interface (API) calls in the `PQPolygonSDK.jl` package are started by creating a `PQPolygonSDKUserModel` object using the function:

```julia    
model(userModelType::Type{PQPolygonSDKUserModel}, 
    options::Dict{String,Any}) -> PQPolygonSDKUserModel
```
where `options` dictionary holds `email` and `apikey` key-value pairs. 

## Endpoint models
The `PQPolygonSDKUserModel` object can then be passed as an argument to a `model` function:

```julia
model(apiModelType::Type{T}, userModel::PQPolygonSDKUserModel, 
        options::Dict{String,Any}) -> AbstractPolygonEndpointModel where T<:AbstractPolygonEndpointModel
```

to build an endpoint-specific model where the information for a particular endpoint is passed into the `model` method via an `options` dictionary.

## Encode a URL string 
The endpoint specific model is then used to create the specific URL for the call using the `url` function: 

```julia
# create the URL string for this endpoint -
my_stock_url_string = url(POLYGON_URL_STRING, stock_endpoint_model);
```

## Make an API call 
Finally, the URL and the API model type are used to make a call against the 
[Polygon.io](https://polygon.io) API:
```julia
# make the API call -
(h_stock, df_stock) = api(PolygonAggregatesEndpointModel, my_stock_url_string);
```
The `api` method returns two pieces of data, a header dictionary holding technical information about the call (and potentially error information of the call failed). The data for the call is returned as a [DataFrame](https://dataframes.juliadata.org/stable/). 
