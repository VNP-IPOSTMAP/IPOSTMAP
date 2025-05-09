# Map events

>IPOSTMAP Android SDK cung cấp các sự kiện của map hay tương tác của người dùng giúp cho nhà phát triển có thể lắng nghe và xử lý.

## Giới thiệu chung

**IPOSTMAP** cung cấp các interface cho phép người dùng thao tác với các sự kiện trên map.

### Các sự kiện thao tác trên Map:

| No | Event Name       | Description                                                                                                             |
|:--:|------------------|-------------------------------------------------------------------------------------------------------------------------|
| 1  | OnCameraMoveStartedListener | Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map chuẩn bị thay đổi  |
| 2  | OnCameraMoveListener        | Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map đang thay đổi      |
| 3  | OnCameraIdleListener        | Được gọi khi các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map kết thúc sự thay đổi         |
| 4  | OnMyLocationClickListener   | Được gọi khi icon My Location trên Map được touch                                                            |
| 5  | OnMyLocationButtonClickListener| Được gọi khi người dùng touch lên nút My Location                                                         |
| 6  | OnMapClickListener          | Được gọi khi có sự kiện touch trên map                                                                       |
| 7  | OnInfoWindowClickListener   | Được gọi khi có sự kiện touch trên info window của Marker                                                    |
| 8  | OnPlaceClickListener        | Được gọi khi có sự kiện touch trên place text khi Map ở chế độ ROADMAP (vector)                              |
| 9  | OnDataSourceFeatureClickListener | Được gọi khi người dùng touch lên các đối tượng của data source custom (không phải dữ liệu của IPOSTMAP)   |

## Hướng dẫn chi tiết

### OnCameraMoveStartedListener

Để lắng nghe sự kiện `OnCameraMoveStartedListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnCameraMoveStartedListener(new Map4D.OnCameraMoveStartedListener() {
    @Override
    public void onCameraMoveStarted(int reason) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnCameraMoveStartedListener(object : Map4D.OnCameraMoveStartedListener {
    override fun onCameraMoveStarted(reason: Int) {

    }
})
```
<!-- tabs:end -->

Tham số `reason` sẽ cho chúng ta biết lý do mà Map thay đổi.

- REASON_GESTURE = 1 : Map thay đổi do người dùng tác động thông qua Gesture.
- REASON_API_ANIMATION = 2 : Map thay đổi do dữ liệu từ API, GPS, ...
- REASON_DEVELOPER_ANIMATION = 3 : Map thay đổi do chúng ta gọi phương thức `animateCamera()` hoặc `moveCamera()`

### OnCameraMoveListener

Để lắng nghe sự kiện `OnCameraMoveListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnCameraMoveListener(new Map4D.OnCameraMoveListener() {
    @Override
    public void onCameraMove() {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnCameraMoveListener(object : Map4D.OnCameraMoveListener {
    override fun onCameraMove() {

    }
})
```
<!-- tabs:end -->

### OnCameraIdleListener

Để lắng nghe sự kiện `OnCameraIdleListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnCameraIdleListener(new Map4D.OnCameraIdleListener() {
    @Override
    public void onCameraIdle() {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnCameraIdleListener(object : Map4D.OnCameraIdleListener {
    override fun onCameraIdle() {

    }
})
```
<!-- tabs:end -->

### OnMyLocationClickListener

Để lắng nghe sự kiện `OnMyLocationClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnMyLocationClickListener(new Map4D.OnMyLocationClickListener() {
    @Override
    public void onMyLocationClick(Location location) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnMyLocationClickListener(object: Map4D.OnMyLocationClickListener {
    override fun onMyLocationClick(location: Location) {

    }
})
```
<!-- tabs:end -->

Tham số `location` sẽ trả về vị trí của marker My Location hiện tại.

### OnMyLocationButtonClickListener

Để lắng nghe sự kiện `OnMyLocationButtonClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnMyLocationButtonClickListener(new Map4D.OnMyLocationButtonClickListener() {
    @Override
    public boolean onMyLocationButtonClick() {
        return false;
    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnMyLocationButtonClickListener(object: Map4D.OnMyLocationButtonClickListener {
    override fun onMyLocationButtonClick(): Boolean {
        return false
    }
})
```
<!-- tabs:end -->

Phương thức `onMyLocationButtonClick()` trả về là `false` thì My Location marker sẽ được cập nhật lại vị trí mới nhất từ
dữ liệu GPS và ngược lại, giá trị trả về là `true` thì My Location marker sẽ không cập nhật lại vị trí mới nhất.

### OnMapClickListener

Để lắng nghe sự kiện `OnMapClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnMapClickListener(new Map4D.OnMapClickListener() {
    @Override
    public void onMapClick(MFLocationCoordinate latLng) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnMapClickListener(object: Map4D.OnMapClickListener {
    override fun onMapClick(latLng: MFLocationCoordinate) {

    }
})
```
<!-- tabs:end -->

Tham số `MFLocationCoordinate` sẽ trả về tọa độ của Map mà chúng ta touch.

### OnInfoWindowClickListener

Để lắng nghe sự kiện `OnInfoWindowClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnInfoWindowClickListener(new Map4D.OnInfoWindowClickListener() {
    @Override
    public void onInfoWindowClick(@NonNull MFMarker marker) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnInfoWindowClickListener(object: Map4D.OnInfoWindowClickListener {
    override fun onInfoWindowClick(marker: MFMarker) {

    }
})
```
<!-- tabs:end -->

Tham số `MFMarker` sẽ trả về Marker có InfoWindow mà chúng ta touch.

### OnPlaceClickListener

Để lắng nghe sự kiện `OnPlaceClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnPlaceClickListener(new Map4D.OnPlaceClickListener() {
    @Override
    public void onPlaceClick(@NonNull String name, @NonNull MFLocationCoordinate location) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnPlaceClickListener(object: Map4D.OnPlaceClickListener {
    override fun onPlaceClick(name: String, location: MFLocationCoordinate) {

    }
})
```
<!-- tabs:end -->

Tham số `String` sẽ trả về tên của place.

Tham số `MFLocationCoordinate` sẽ trả về tọa độ của place.

### OnDataSourceFeatureClickListener

Để lắng nghe sự kiện `OnDataSourceFeatureClickListener` chúng ta làm như sau:

<!-- tabs:start -->
#### ** Java **

```java
private Map4D map4D;

map4D.setOnDataSourceFeatureClickListener(new Map4D.OnDataSourceFeatureClickListener() {
    @Override
    public void onDataSourceFeatureClick(@NonNull MFDataSourceFeature dataSourceFeature, @NonNull MFLocationCoordinate location) {

    }
});
```

#### ** Kotlin **

```kotlin
private lateinit var map4D: Map4D

map4D.setOnDataSourceFeatureClickListener(object: Map4D.OnDataSourceFeatureClickListener {
    override fun onDataSourceFeatureClick(dataSourceFeature: MFDataSourceFeature, location: MFLocationCoordinate) {

    }
})
```
<!-- tabs:end -->

Tham số `MFDataSourceFeature` sẽ trả về features của đối tượng data source.

Tham số `MFLocationCoordinate` sẽ trả về tọa độ của đối tượng data source.
