# Map reference

## MFMapView

### 1. Constructor 

<!-- tabs:start -->
#### ** Swift **

```swift
let mapView = MFMapView(frame: self.view.frame)
let mapView = MFMapView(frame: self.view.frame, mapID: MFMapID(identifier: "map_id"))
```

#### ** Objective C **

```objc
MFMapView *mapView = [[MFMapView alloc] initWithFrame:self.view.frame];
MFMapView *mapView = [[MFMapView alloc] initWithFrame:self.view.frame identifier:[MFMapID mapIDWithIdentifier:@"map_id"]];
```
<!-- tabs:end -->

### 2. Properties

| Name                       | Type                                                                            |
|----------------------------|:--------------------------------------------------------------------------------|
| **delegate**               | [MFMapViewDelegate](/guides/map-events?id=Map-events)                           |
| **projection**             | [MFProjection](/guides/projection?id=Projection)                                |
| **camera**                 | [MFCameraPosition](/reference/map?id=MFCameraPosition)                          | 
| **settings**               | [MFUISettings](/reference/map?id=MFUISettings)                                  |
| **mapType**                | [MFMapType](/reference/map?id=MFMapType)                                  |
| **nativeScale**            | CGFloat                                                                         |


### 3. Methods

| Name                       | Parameters              | Return value         | Description                                                                                                             |
|----------------------------|-------------------------|----------------------|-------------------------------------------------------------------------------------------------------------------------|
| **setMyLocationEnabled**   | BOOL                    | void                 | Bật vị trí của thiết bị                                                                                                 |
| **getMyLocation**          | none                    | CLLocation           | Lấy vị trí của thiết bị                                                                                                 |
| **setPOIsEnabled**         | BOOL                    | void                 | Cho phép hiển thị các **POI** có sẵn của **map** hay không                                                              |
| **isPOIsEnabled**          | none                    | BOOL                 | Kiểm tra các **POI** có sẵn của **map** được phép hiển thị hay không.                                                   |
| **setBuildingsEnabled**    | BOOL                    | void                 | Cho phép hiển thị các **Building** có sẵn của **map** trong chế độ 3D hay không.                                        |
| **isBuildingsEnabled**     | none                    | BOOL                 | Kiểm tra các **Building** có sẵn của **map** được phép hiển thị trong chế độ 3D hay không.                              |
| **setSelectedBuildings**   | [NSString]?             | void                 | **Set** **high light** cho các **Building** có **id** nằm trong danh sách tham số truyền vào trong chế độ 3D.           |
| **setMaxNativeZoom**       | Double                  | void                 | **Set** mức **zoom** lớn nhất mà **map** **request tile** từ **server**.                                                |
| **setTileUrl**             | NSString                | void                 | **Set** một đường dẫn **url** để tải **tile** từ **server** thay thế cho **url** mặc định của SDK.                      |
| **setMinZoom**             | Double, Double          | void                 | **Set** mức **zoom** nhỏ nhất và lớn nhất mà **map** có thể hiển thị.                                                   |
| **clear**                  | BOOL                    | void                 | Xoá mọi thứ mà người dùng **add** vào như **Markers**, **Polylines**, **POI**, **Building**.       |
| **setTime**                | Double, Double          | void                 | **Set** thời gian hiển thị cho **map**.                                                                                 |
| **enableWaterEffect**      | BOOL                    | void                 | Bật hoặc tắt hiệu ứng nước khi set map type là 3D của **map**..                                                         |
| **cameraForBounds**        | [MFCoordinateBounds](/reference/coordinates?id=MFCoordinateBounds)                 | [MFCameraPosition](/reference/map?id=MFCameraPosition)   | Tạo ra một thông tin **Camera** từ các tham số bạn truyền vào. |
| **cameraForBounds**        | [MFCoordinateBounds](/reference/coordinates?id=MFCoordinateBounds) , UIEdgeInsets  | [MFCameraPosition](/reference/map?id=MFCameraPosition)   | Tạo ra một thông tin **Camera** từ các tham số bạn truyền vào. |
| **animateCamera**          | [MFCameraUpdate](/reference/map?id=MFCameraUpdate)                         | none                 | **Animate** **camera** đến vị trí theo camera bạn truyền vào.        |
| **moveCamera**             | [MFCameraUpdate](/reference/map?id=MFCameraUpdate)                         | none                 | **Move** **camera** đến vị trí theo camera bạn truyền vào.           |
| **getBounds**              | none         | [MFCoordinateBounds](/reference/coordinates?id=MFCoordinateBounds)                 | Lấy khu vực hiển thị của map hiện tại.                               |
| **metersForPoints**        | double                  | double               | Convert giá trị từ point sang mét |
| **pointsForMeters**        | double                  | double               | Convert giá trị từ mét sang point |
| **setMapID**               | [MFMapID](/reference/map?id=MFMapID) | void    | Set Map ID |

### MFCameraPosition

#### 1. Constructor 

<!-- tabs:start -->
#### ** Swift **

```swift
init(target: CLLocationCoordinate2D, zoom: Double) {}
init(target: CLLocationCoordinate2D, zoom: Double, tilt: Double) {}
init(target: CLLocationCoordinate2D, zoom: Double, bearing: Double) {}
init(target: CLLocationCoordinate2D, zoom: Double, tilt: Double, bearing: Double) {}
```

#### ** Objective C **

```objc  
- (instancetype)initWithTarget:(CLLocationCoordinate2D) target zoom: (double) zoom;
- (instancetype)initWithTarget:(CLLocationCoordinate2D) target zoom: (double) zoom tilt :(double) tilt ;
- (instancetype)initWithTarget:(CLLocationCoordinate2D) target zoom: (double) zoom bearing: (double) bearing;
- (instancetype)initWithTarget:(CLLocationCoordinate2D) target zoom: (double) zoom tilt :(double) tilt bearing: (double) bearing;
```
<!-- tabs:end -->

#### 2. Properties

| Name                       | Type                                                                            |
|----------------------------|:--------------------------------------------------------------------------------|
| **target**                 | CLLocationCoordinate2D                                                          |
| **zoom**                   | double                                                                          |
| **bearing**                | double                                                                          | 
| **tilt**                   | double                                                                          |

### MFCameraUpdate

#### Public static member functions 

<!-- tabs:start -->
#### ** Swift **

```swift
class func fit(_ bounds: MFCoordinateBounds?) -> MFCameraUpdate? {}
class func fit(_ bounds: MFCoordinateBounds?, with edgeInsets: UIEdgeInsets) -> MFCameraUpdate? {}
class func setTarget(_ target: CLLocationCoordinate2D) -> MFCameraUpdate? {}
class func setTarget(_ target: CLLocationCoordinate2D, zoom: Double) -> MFCameraUpdate? {}
class func setTarget(_ target: CLLocationCoordinate2D, zoom: Double, tilt: Double) -> MFCameraUpdate? {}
class func setTarget(_ target: CLLocationCoordinate2D, zoom: Double, bearing: Double) -> MFCameraUpdate? {}
class func setTarget(_ target: CLLocationCoordinate2D, zoom: Double, tilt: Double, bearing: Double) -> MFCameraUpdate? {}
class func setCamera(_ camera: MFCameraPosition?) -> MFCameraUpdate? {}
```

#### ** Objective C **

```objc  
+ (MFCameraUpdate *) fitBounds: (MFCoordinateBounds *) _bounds;
+ (MFCameraUpdate *) fitBounds:(MFCoordinateBounds *) _bounds withEdgeInsets:(UIEdgeInsets) _edgeInsets;
+ (MFCameraUpdate *)setTarget:(CLLocationCoordinate2D) target;
+ (MFCameraUpdate *)setTarget:(CLLocationCoordinate2D) target zoom: (double) zoom;
+ (MFCameraUpdate *)setTarget:(CLLocationCoordinate2D) target zoom: (double) zoom tilt :(double) tilt;
+ (MFCameraUpdate *)setTarget:(CLLocationCoordinate2D) target zoom: (double) zoom bearing: (double) bearing;
+ (MFCameraUpdate *)setTarget:(CLLocationCoordinate2D) target zoom: (double) zoom tilt :(double) tilt bearing: (double) bearing;
+ (MFCameraUpdate *)setCamera:(MFCameraPosition *) camera;
```
<!-- tabs:end -->

### MFUISettings

#### 1. Properties

| Name                       | Type                                                                            |
|----------------------------|:--------------------------------------------------------------------------------|
| **myLocationButton**       | CLLocationCoordinate2D                                                          |
| **scrollGestures**         | double                                                                          |
| **zoomGestures**           | double                                                                          | 
| **tiltGestures**           | double                                                                          |
| **rotateGestures**         | double                                                                          |

#### 3. Methods

| Name                       | Parameters                | Return value         | Description                                                                         |
|----------------------------|:-------------------------:|:--------------------:|-------------------------------------------------------------------------------------|
| **setAllGesturesEnabled**  | BOOL                      | void                 | Bật hoặc tắt tất cả cử chỉ tương tác với **map**                                    |

### MFMapType

`MFMapType` enum

| Name                       | Description                                                                     |
|----------------------------|:--------------------------------------------------------------------------------|
| **MFMapTypeRoadmap**       | Map hiển thị tiles ở dạng vector                                                |
| **MFMapTypeSatellite**     | Map hiển thị tiles ở dạng hình ảnh vệ tinh, không bao gồm thông tin đường sá    |
| **MFMapTypeHybrid**        | Map hiển thị tiles ở dạng hình ảnh vệ tinh, kết hợp thông tin đường sá          |

### MFMapID

`MFMapID` class

#### Public static member functions

```objc
/** Creates a new mapID with the given string value. */
+ (instancetype)mapIDWithIdentifier:(NSString *)identifier NS_SWIFT_UNAVAILABLE("Use initializer instead");
```