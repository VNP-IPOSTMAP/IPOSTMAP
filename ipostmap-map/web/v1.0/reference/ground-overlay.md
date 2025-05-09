# Ground Overlay References

## GroundOverlay class

`map4d.GroundOverlay` class

**Constructor**

Tạo GroundOverlay với các options được chỉ định

```js
GroundOverlay(options)
```

- Parameters:
  - options: [GroundOverlayOptions](/ipostmap-map/web/v1.0/reference/ground-overlay.md?id=groundoverlayoptions-interface) *required*


**Methods**

| Name           | Parameters                              | Return Value | Description                                                                                |
|----------------|-----------------------------------------|:------------:|--------------------------------------------------------------------------------------------|
| **setMap**     | map: [Map](/ipostmap-map/web/v1.0/reference/map.md?id=map-class) | `none`       | Hiển thị ground overlay lên map, nếu set map là null thì ground overlay sẽ bị xóa khỏi map |
| **setVisible** | visibility: boolean                     | `none`       | Ẩn/hiện ground overlay trên map                                                            |
| **isVisible**  | `none`                                  | boolean      | Get trạng thái ẩn/hiện của overlay                                                         |
| **setZIndex**  | zIndex: number                          | `none`       | Set giá trị zIndex                                                                         |
| **getZIndex**  | `none`                                  | number       | Get giá trị zIndex hiện tại của overlay                                                    |
| **setOpacity** | number                                  | `none`       | Set giá trị opacity cho overlay. Giá trị opacity từ 0 đến 1                                |
| **getOpacity** | `none`                                  | number       | Get giá trị opacity hiện tại của overlay                                                   |

## GroundOverlayOptions interface

`map4d.GroundOverlayOptions` interface

Đối tượng GroundOverlayOptions đùng để xác định các thuộc tính dùng cho TileOverlay.

**Properties**

| Name                    | Type                                                     | Description                                                                                                          |
|-------------------------|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **getUrl** *required*   | function                                                 | Hàm nhận vào 4 giá trị `x`, `y`, `zoom`, `is3dMode` và trả về đường dẫn đến map tile                                 |
| **bounds** *required*   | [ILatLngBounds](/ipostmap-map/web/v1.0/reference/coordinates.md?id=ilatlngbounds) | Vùng hiển thị ground overlay                                                                                         |
| **override** *optional* | boolean                                                  | Cho phép hiển thị ground overlay đè hoàn toàn lên Map4D, vùng hiển thị ground overlay sẽ không tải dữ liệu của Map4D |
| **visible** *optional*  | boolean                                                  | Nếu là true thì ground overlay sẽ được hiển thị                                                                      |
| **zIndex** *optional*   | number                                                   | Thứ tự hiển thị của ground overlay (đối với ground overlay khác và tile overlay)                                     |
| **opacity** *optional*  | number                                                   | Độ trong suốt của ground overlay. Có giá trị từ 0 đến 1                                                              |
