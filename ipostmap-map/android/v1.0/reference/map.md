# Map reference

## Map4D class

Các phương thức:

| Name                    | Parameters       | Return Value | Description                                                                            |
|-------------------------|------------------|--------------|----------------------------------------------------------------------------------------|
| **getMyLocation**       | boolean          | `none`       | Lấy vị trí hiện tại của My Location marker                                             |
| **getCameraPosition**   |`none`|[MFCameraPosition](/reference/map?id=mfcameraposition)| Get thông số Camera Postion của Map                        |
| **getBounds**           |`none`|[MFCoordinateBounds](/reference/coordinates?id=mfcoordinatebounds)| Get vùng bounds của Map với các thông số Camera và màn hình hiện tại. |
| **getCameraPositionForBounds**|[MFCoordinateBounds](/reference/coordinates?id=mfcoordinatebounds), int|[MFCameraPosition](/reference/map?id=mfcameraposition)| Tạo một Camera Position từ tham số bounds và padding|
| **getCameraPositionForBounds**|[MFCoordinateBounds](/reference/coordinates?id=mfcoordinatebounds), int, int, int, int|[MFCameraPosition](/reference/map?id=mfcameraposition)| Tạo một Camera Position từ tham số bounds và padding|
| **getProjection**       | `none`|[MFProjection](/guides/projection?id=projection)| Get thuộc tính MFProjection của Map                             |
| **getUiSettings**       | `none`|[MFUiSettings](/reference/map?id=mfuisettings)| Get thuộc tính cài đặt giao diện của Map                          |
| **addMarker**           |[MFMarkerOptions](/reference/marker?id=marker-options)|[MFMarker](/reference/marker?id=mfmarker-class)| Add một marker vào Map|
| **addPolyline**         |[MFPolylineOptions](/reference/polyline?id=polyline-options)|[MFPolyline](/reference/polyline?id=polyline-class)| Add một polyline vào Map|
| **addPolygon**          |[MFPolygonOptions](/reference/polygon?id=polygon-options)|[MFPolygon](/reference/polygon?id=polygon-class)| Add một polygon vào Map|
| **addCircle**           |[MFCircleOptions](/reference/circle?id=circle-options)|[MFCircle](/reference/circle?id=circle-class)| Add một circle vào Map|
| **addPOI**              |[MFPOIOptions](/reference/poi?id=poi-options)|[MFPOI](/reference/poi?id=poi-class)| Add một POI vào Map                   |
| **addBuilding**         |[MFBuildingOptions](/reference/building?id=building-options)|[MFBuilding](/reference/building?id=building-class)| Add một Building vào Map |
| **addTileOverlay**      |[MFTileOverlayOptions](/reference/tile-overlay?id=mftileoverlayoptions-class)|[MFTileOverlay](/reference/tile-overlay?id=mftileoverlay-class)| Add một Tile Overlay vào Map |
| **addBuildingOverlay**  |[MFBuildingOverlayOptions](/reference/building-overlay?id=mfbuildingoverlayoptions-class)|[MFBuildingOverlay](/reference/building-overlay?id=buildingoverlay-class)| Add một Building Overlay vào Map |
| **addPOIOverlay**       |[MFPOIOverlayOptions](/reference/poi-overlay?id=mfpoioverlayoptions-class)|[MFPOIOverlay](/reference/poi-overlay?id=poioverlay-class)| Add một POI Overlay vào Map |
| **moveCamera**          |[MFCameraUpdate](/reference/map?id=mfcameraupdate)|`none`| Di chuyển bản đồ tới một vị trí Camera ngay lập tức            |
| **animateCamera**       |[MFCameraUpdate](/reference/map?id=mfcameraupdate)|`none`| Di chuyển bản đồ tới một vị trí Camera với hiệu ứng fly        |
| **isMyLocationEnabled** | `none`           | boolean      | Kiểm tra xem My Location marker có được hiển thị hay không                             |
| **setMyLocationEnabled**| boolean          | `none`       | Set giá trị enable cho My Location marker                                              |
| **setTime**             | Date             | `none`       | Set giá trị thời gian cho Map                                                          |
| **setOnMyLocationButtonClickListener**|`Map4D.OnMyLocationButtonClickListener`|`none`| Set một callback để bắt sự kiện nút My Location được ấn     |
| **setOnMarkerClickListener**|`Map4D.OnMarkerClickListener`|`none`| Set một callback để bắt sự kiện touch lên Marker                                |
| **setOnMarkerDragListener**|`Map4D.OnMarkerDragListener`|`none`| Set một callback để bắt sự kiện kéo Marker trên Map                               |
| **setOnMyLocationClickListener**|`Map4D.OnMyLocationClickListener`|`none`| Set một callback để bắt sự kiện khi touch My Location marker            |
| **setOnPolylineClickListener**|`Map4D.OnPolylineClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên Polyline                      |
| **setOnPolygonClickListener**|`Map4D.OnPolygonClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên Polygon                         |
| **setOnCircleClickListener**|`Map4D.OnCircleClickListener`|`none| Set một callback để bắt sự kiện khi touch lên Circle                             |
| **setMaxZoomPreference**| double           | `none`       | Set giá trị zoom lớn nhất mà Map có thể hiển thị                                       |
| **setMinZoomPreference**| double           | `none`       | Set giá trị zoom nhỏ nhất mà Map có thể hiển thị                                       |
| **setMaxNativeZoom**    | double           | `none`       | Set giá trị zoom lớn nhất mà Tile không bị scale khi Map hiển thị                      |
| **setOnMapClickListener**|`Map4D.OnMapClickListener`|`none`| Set một callback để bắt sự kiện touch lên Map                                         |
| **setOnCameraMoveStartedListener**|`Map4D.OnCameraMoveStartedListener`|`none`| Set một callback để bắt sự kiện Camera của Map bắt đầu thay đổi     |
| **setOnCameraMoveListener**|`Map4D.OnCameraMoveListener`|`none`| Set một callback để bắt sự kiện Camera của Map đang thay đổi                      |
| **setOnCameraIdleListener**|`Map4D.OnCameraIdleListener`|`none`| Set một callback để bắt sự kiện Camera của Map thay đổi xong                      |
| **setOnBuildingClickListener**|`Map4D.OnBuildingClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên Building                      |
| **setOnBuildingClickListener**|`Map4D.OnBuildingClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên Building                      |
| **setOnUserBuildingClickListener**|`Map4D.OnUserBuildingClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên User Building         |
| **setOnPOIClickListener**|`Map4D.OnPOIClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên POI                                     |
| **setOnUserPOIClickListener**|`Map4D.OnUserPOIClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên User POI                        |
| **setOnInfoWindowClickListener**|`Map4D.OnInfoWindowClickListener`|`none`| Set một callback để bắt sự kiện khi touch lên Info Window               |
| **getSelectedPlace**    | `none`           | String       | Get id của POI được chọn (selected)                                                    |
| **setInfoWindowAdapter**|`Map4D.InfoWindowAdapter`|`none` | Set info window adapter cho Map                                                        |
| **setPOIsEnabled**      | boolean          | `none`       | Set tất cả các POI của Map4D hiện hay ẩn                                               |
| **isPOIsEnabled**       | `none`           | boolean      | Kiểm tra POI của Map4D có hiện hay không                                               |
| **setBuildingsEnabled** | boolean          | `none`       | Set tất cả các Building của Map4D hiện hay ẩn                                          |
| **isBuildingsEnabled**  | `none`           | boolean      | Kiểm tra Building của Map4D có được hiện hay không                                     |
| **setSelectedBuildings**| List< String >   | `none`       | Set các Building sẽ được hightlight theo danh sách id truyền vào                       |
| **setWaterEffectEnabled**| boolean         | `none`       | Bật hoặc tắt hiệu ứng nước 3D của Map                                                  |
| **setScrollGesturesEnabled**| boolean      | `none`       | Bật hoặc tắt cử chỉ di chuyển Map                                                      |
| **setZoomGesturesEnabled**| boolean        | `none`       | Bật hoặc tắt cử chỉ phóng to hoặc thu nhỏ Map                                          |
| **setRotateGesturesEnabled**| boolean      | `none`       | Bật hoặc tắt cử chỉ xoay Map                                                           |
| **setTiltGesturesEnabled**| boolean        | `none`       | Bật hoặc tắt cử chỉ nghiêng Map                                                        |
| **setAllGesturesEnabled**| boolean         | `none`       | Bật hoặc tắt tất cả các cử chỉ tác động lên Map                                        |
| **setMapType**          |[MFMapType](/reference/map?id=mfmaptype)| `none` | Set kiểu của tile cho Map (Raster hoặc Vector)                         |
| **getMapType**          |`none`|[MFMapType](/reference/map?id=mfmaptype)  | Trả về kiểu hiện thị của tile Map hiện tại                             |
| **setMapId**            | String           | `none`       | Set Map ID                                                      |
| **getMapId**            | `none`           | String       | Trả về Map ID hiện tại                                          |
| **clear**               | `none`           | `none`       | Xóa tất cả các Annotation ra khỏi Map                                                  |

## MFCameraPosition.Builder

Constructor:

| No | Name                         |
|----|------------------------------|
| 1  | Builder()                    |
| 2  | Builder(CameraPositionUpdate)|
| 3  | Builder(CameraZoomUpdate)    |
| 4  | Builder(MFCameraPosition)    |

Các phương thức:

| Name        | Parameters   | Return Value | Description                                                                         |
|-------------|--------------|--------------|-------------------------------------------------------------------------------------|
| **target**  |[MFLocationCoordinate](/reference/coordinates?id=mflocationcoordinate)|Builder| trả về một `Builder` với target được thêm vào                                    |
| **zoom**    | double       | Builder      | trả về một `Builder` với zoom được thêm vào                                         |
| **tilt**    | double       | Builder      | trả về một `Builder` với tilt được thêm vào                                         |
| **bearing** | double       | Builder      | trả về một `Builder` với bearing được thêm vào                                      |
| **build**   | `none`       |[MFCameraPosition](/reference/map?id=mfcameraposition)| tạo một `MFCameraPosition` từ đối tượng `Builder`|

## MFCameraPosition

Để tạo một đối tượng `MFCameraPosition` thì ta dùng class static [MFCameraPosition.Builder](/reference/map?id=mfcamerapositionbuilder)

Các phương thức:

| Name        | Parameters   | Return Value | Description                                                                         |
|-------------|--------------|--------------|-------------------------------------------------------------------------------------|
| `static` **fromCoordinateZoom**|[MFLocationCoordinate](/reference/coordinates?id=mflocationcoordinate), double|MFCameraPosition| trả về một `MFCameraPosition` với target và mức zoom|
| **getTarget**| `none`      | [MFLocationCoordinate](/reference/coordinates?id=mflocationcoordinate) | trả về target của camera                                                |
| **getZoom**  | `none`      | double       | trả về mức zoom của camera                                                          |
| **getTilt**  | `none`      | double       | trả về độ nghiêng của camera                                                        |
| **getBearing**|`none`      |MFCameraPosition| trả về góc xoay của camera                                                        |

## MFCameraUpdate

`MFCameraUpdate` là một interface

Các phương thức:

| Name                   | Parameters   | Return Value | Description                                                                         |
|------------------------|--------------|--------------|-------------------------------------------------------------------------------------|
| **getCameraPosition**  |[Map4D](/reference/map?id=map4d-class)|MFCameraPosition| trả về Camera Position của Map4D                          |

## MFCameraUpdateFactory

`MFCameraUpdateFactory` class chứa các phương thức để tạo một đối tượng `MFCameraUpdate`

Các phương thức:

| Name                              | Parameters   | Return Value | Description                                                                         |
|-----------------------------------|--------------|--------------|-------------------------------------------------------------------------------------|
| `static` **newCameraPosition**    |[MFCameraPosition](/reference/map?id=mfcameraposition)|MFCameraUpdate| trả về MFCameraUpdate từ một camera position|
| `static` **newCoordinate**        |[MFLocationCoordinate](/reference/coordinates?id=mflocationcoordinate)|MFCameraUpdate| trả về MFCameraUpdate từ một tọa độ      |
| `static` **newCoordinateBounds**  |[MFCoordinateBounds](/reference/coordinates?id=mfcoordinatebounds), int|MFCameraUpdate| trả về MFCameraUpdate từ một vùng bounds và padding      |
| `static` **newCoordinateBounds**  |[MFCoordinateBounds](/reference/coordinates?id=mfcoordinatebounds), int, int, int, int|MFCameraUpdate| trả về MFCameraUpdate từ một vùng bounds và padding|
| `static` **newCoordinateZoom**    |[MFLocationCoordinate](/reference/coordinates?id=mflocationcoordinate), double|MFCameraUpdate| trả về MFCameraUpdate từ một tọa độ và mức zoom |
| `static` **zoomIn**               | `none`       | MFCameraUpdate| trả về MFCameraUpdate của mức zoom lớn hơn 1 đơn vị so với hiện tại |
| `static` **zoomOut**              | `none`       | MFCameraUpdate| trả về MFCameraUpdate của mức zoom nhỏ hơn 1 đơn vị so với hiện tại |
| `static` **zoomTo**               | double       | MFCameraUpdate| trả về MFCameraUpdate của mức zoom mà chúng ta truyền vào           |


## MFUiSettings

`MFUiSettings` dùng để cài đặt các chức năng trên giao diện người dùng của Map.

Các phương thức:

| Name                            | Parameters | Return Value | Description                                                                     |
|---------------------------------|------------|--------------|---------------------------------------------------------------------------------|
| **isMyLocationButtonEnabled**   | `none`     | boolean      | Kiểm tra nút My Location có được bật hay không                                  |
| **isZoomGesturesEnabled**       | `none`     | boolean      | Kiểm tra điều khiển Zoom bằng cử chỉ của Map có được bật hay không              |
| **isRotateGesturesEnabled**     | `none`     | boolean      | Kiểm tra điều khiển Rotate bằng cử chỉ của Map có được bật hay không            |
| **isTiltGesturesEnabled**       | `none`     | boolean      | Kiểm tra điều khiển Tilt bằng cử chỉ của Map có được bật hay không              |
| **isScrollGesturesEnabled**     | `none`     | boolean      | Kiểm tra điều khiển di chuyển bằng cử chỉ của Map có được bật hay không         |
| **setMyLocationButtonEnabled**  | boolean    | `none`       | Hiện hoặc ẩn My Location Button                                                 |
| **setZoomGesturesEnabled**      | boolean    | `none`       | Bật hoặc tắt việc phóng to, thu nhỏ Map bằng cử chỉ                             |
| **setScrollGesturesEnabled**    | boolean    | `none`       | Bật hoặc tắt việc di chuyển Map bằng cử chỉ                                     |
| **setRotateGesturesEnabled**    | boolean    | `none`       | Bật hoặc tắt việc xoay Map bằng cử chỉ                                          |
| **setTiltGesturesEnabled**      | boolean    | `none`       | Bật hoặc tắt việc nghiêng Map bằng cử chỉ                                       |
| **setAllGesturesEnabled**       | boolean    | `none`       | Bật hoặc tắt tất cả các cử chỉ để điều khiển Map                                |


## MFMapType

`MFMapType` dùng để định nghĩa kiểu của tile Map.

* RASTER: Kiểu tile hiển thị trên Map là raster.
* ROADMAP: Kiểu tile hiển thị trên Map là vector.

## Map ID

> Để có thể thay đổi Style của Map thì chúng ta phải thông qua `mapId`.

#### Tạo mapdId

Một `mapID` là một định danh duy nhất đại diện cho một instance duy nhất của Map4D. Bạn có thể tạo `mapID` và liên kết với map style thông qua
[trang quản lý của Map4D](https://map.map4d.vn/developer/mapstyle)

#### Thêm mapId vào ứng dụng

Để thêm `mapId` vào ứng dụng thì chúng ta sử dụng thuộc tính `map:mapId` của lớp `MFMapView` trong file layout của activity như bên dưới:

```xml
<vn.map4d.map.core.MFMapView
    xmlns:map="http://schemas.android.com/apk/res-auto"
    ....
    map:mapId="YOUR_MAP_ID" />
```
