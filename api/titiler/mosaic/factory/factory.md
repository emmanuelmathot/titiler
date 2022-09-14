# Module titiler.mosaic.factory

TiTiler.mosaic Router factories.

None

## Variables

```python3
MAX_THREADS
```

```python3
img_endpoint_params
```

## Functions

    
### PixelSelectionParams

```python3
def PixelSelectionParams(
    pixel_selection: titiler.mosaic.resources.enums.PixelSelectionMethod = Query(first)
) -> rio_tiler.mosaic.methods.base.MosaicMethodBase
```

    
Returns the mosaic method used to combine datasets together.

## Classes

### MosaicTilerFactory

```python3
class MosaicTilerFactory(
    reader: Type[cogeo_mosaic.backends.base.BaseBackend] = <function MosaicBackend at 0x7f0d7292cc10>,
    router: fastapi.routing.APIRouter = <factory>,
    path_dependency: Callable[..., Any] = <function DatasetPathParams at 0x7f0d72115c10>,
    dataset_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.DatasetParams'>,
    layer_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.BidxExprParams'>,
    render_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.ImageRenderingParams'>,
    colormap_dependency: Callable[..., Union[Dict[int, Tuple[int, int, int, int]], Sequence[Tuple[Tuple[Union[float, int], Union[float, int]], Tuple[int, int, int, int]]], NoneType]] = <function ColorMapParams at 0x7f0d72298160>,
    stats_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.StatisticsParams'>,
    histogram_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.HistogramParams'>,
    process_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.PostProcessParams'>,
    tms_dependency: Callable[..., morecantile.models.TileMatrixSet] = <function WebMercatorTMSParams at 0x7f0d7227aee0>,
    reader_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.DefaultDependency'>,
    environment_dependency: Callable[..., Dict] = <function BaseTilerFactory.<lambda> at 0x7f0d7a92a940>,
    router_prefix: str = '',
    optional_headers: List[titiler.core.resources.enums.OptionalHeader] = <factory>,
    route_dependencies: List[Tuple[List[titiler.core.routing.EndpointScope], List[fastapi.params.Depends]]] = <factory>,
    dataset_reader: Union[Type[rio_tiler.io.base.BaseReader], Type[rio_tiler.io.base.MultiBaseReader], Type[rio_tiler.io.base.MultiBandReader]] = <class 'rio_tiler.io.cogeo.COGReader'>,
    backend_dependency: Type[titiler.core.dependencies.DefaultDependency] = <class 'titiler.core.dependencies.DefaultDependency'>,
    pixel_selection_dependency: Callable[..., rio_tiler.mosaic.methods.base.MosaicMethodBase] = <function PixelSelectionParams at 0x7f0d7292caf0>
)
```

#### Ancestors (in MRO)

* titiler.core.factory.BaseTilerFactory

#### Class variables

```python3
backend_dependency
```

```python3
dataset_dependency
```

```python3
dataset_reader
```

```python3
histogram_dependency
```

```python3
layer_dependency
```

```python3
process_dependency
```

```python3
reader_dependency
```

```python3
render_dependency
```

```python3
router_prefix
```

```python3
stats_dependency
```

#### Methods

    
#### add_route_dependencies

```python3
def add_route_dependencies(
    self,
    *,
    scopes: List[titiler.core.routing.EndpointScope],
    dependencies=typing.List[fastapi.params.Depends]
)
```

    
Add dependencies to routes.

Allows a developer to add dependencies to a route after the route has been defined.

    
#### assets

```python3
def assets(
    self
)
```

    
Register /assets endpoint.

    
#### bounds

```python3
def bounds(
    self
)
```

    
Register /bounds endpoint.

    
#### colormap_dependency

```python3
def colormap_dependency(
    colormap_name: titiler.core.dependencies.ColorMapName = Query(None),
    colormap: str = Query(None)
) -> Union[Dict[int, Tuple[int, int, int, int]], Sequence[Tuple[Tuple[Union[float, int], Union[float, int]], Tuple[int, int, int, int]]], NoneType]
```

    
Colormap Dependency.

    
#### environment_dependency

```python3
def environment_dependency(
    
)
```

    

    
#### info

```python3
def info(
    self
)
```

    
Register /info endpoint

    
#### path_dependency

```python3
def path_dependency(
    url: str = Query(Ellipsis)
) -> str
```

    
Create dataset path from args

    
#### pixel_selection_dependency

```python3
def pixel_selection_dependency(
    pixel_selection: titiler.mosaic.resources.enums.PixelSelectionMethod = Query(first)
) -> rio_tiler.mosaic.methods.base.MosaicMethodBase
```

    
Returns the mosaic method used to combine datasets together.

    
#### point

```python3
def point(
    self
)
```

    
Register /point endpoint.

    
#### read

```python3
def read(
    self
)
```

    
Register / (Get) Read endpoint.

    
#### reader

```python3
def reader(
    input: str,
    *args: Any,
    **kwargs: Any
) -> cogeo_mosaic.backends.base.BaseBackend
```

    
Select mosaic backend for input.

    
#### register_routes

```python3
def register_routes(
    self
)
```

    
This Method register routes to the router.

Because we wrap the endpoints in a class we cannot define the routes as
methods (because of the self argument). The HACK is to define routes inside
the class method and register them after the class initialization.

    
#### tile

```python3
def tile(
    self
)
```

    
Register /tiles endpoints.

    
#### tilejson

```python3
def tilejson(
    self
)
```

    
Add tilejson endpoint.

    
#### tms_dependency

```python3
def tms_dependency(
    TileMatrixSetId: titiler.core.dependencies.WebMercatorTileMatrixSetName = Query(WebMercatorTileMatrixSetName.WebMercatorQuad)
) -> morecantile.models.TileMatrixSet
```

    
TileMatrixSet Dependency.

    
#### url_for

```python3
def url_for(
    self,
    request: starlette.requests.Request,
    name: str,
    **path_params: Any
) -> str
```

    
Return full url (with prefix) for a specific endpoint.

    
#### validate

```python3
def validate(
    self
)
```

    
Register /validate endpoint.

    
#### wmts

```python3
def wmts(
    self
)
```

    
Add wmts endpoint.