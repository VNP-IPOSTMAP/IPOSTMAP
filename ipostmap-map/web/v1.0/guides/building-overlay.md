# Building Overlay

Building overlay là một loại overlay cho phép người dùng hiển thị các building từ nhiều nguồn khác nhau lên bản đồ, kết hợp với building sẵn có của IPOSTMAP.  
Building overlay chỉ hiển thị ở chế độ 3D.

## Add Building overlay

Để thêm 1 building overlay vào map cần tạo mới 1 đối tượng của lớp [BuildingOverlay](/ipostmap-map/web/v1.0/reference/building-overlay.md?id=buildingverlay-class) sau đó set `map` cho building overlay đó.  
Hàm khởi tạo của lớp [BuildingOverlay](/ipostmap-map/web/v1.0/reference/building-overlay.md?id=buildingoverlay-class) nhận vào một đối tượng [BuildingOverlayOptions](/ipostmap-map/web/v1.0/reference/building-overlay.md?id=buildingoverlayoptions-interface) có các tham số như sau:

|  No | Property   | Type     | Requied | Description                                                                                                                                                                        |
|:---:|------------|----------|:-------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  1  | getUrl     | function |   YES   | Hàm nhận vào 3 giá trị `x`, `y`, `zoom` và trả về đường dẫn đến Buildings                                                                                                          |
|  2  | parserData | function |   YES   | Hàm nhận vào response data từ api của `getUrl` và parser thành mảng các [BuildingData](/ipostmap-map/web/v1.0/reference/building-overlay.md?id=buildingdata-interface)                                 |
|  3  | prefixId   | string   |    NO   | Giá trị được thêm vào trước id của những building thuộc building overlay.<br>Dùng để tránh nhầm lẫn trong trường hợp trùng id với building của Map4D hay các building overlay khác |
|  4  | visible    | boolean  |    NO   | Nếu `true` thì building overlay sẽ được hiển thị                                                                                                                                   |

### Tạo mới Building overlay

```js
let options = {
  getUrl: function (x, y, zoom) {
    return `rest-api-get-building-from-tile-coordinate`
  },
  parserData: function(response) {
    let buildingDatas = []
    /**
     * parser data from response ...
     */
    return buildingDatas
  },
  prefixId: "prefix"
  visible: true
}
let overlay = new map4d.BuildingOverlay(options)
```

### Add Building overlay lên Map

Để vẽ building overlay lên map, ta set map cho building overlay bằng hàm `setMap`

```js
overlay.setMap(map)
```

### Remove Building overlay

Để xóa building overlay khỏi map, ta gọi hàm `setMap` và truyền vào giá trị `null`

```js
overlay.setMap(null)
```

### Ẩn/Hiện Building Overlay

Gọi hàm `setVisible(boolean)` để ẩn/hiện building overlay.  
Chú ý: Mặc dù building overlay không hiển thị nhưng quá trình tải các building vẫn diễn ra

```js
overlay.setVisible(false)
```

## Sự kiện đối với building thuộc building overlay

Các sự kiện đối với building thuộc building overlay phát sinh tương tự với building của Map4D, việc xử lý được diễn ra ngay tại hàm xử lý sự kiện của Map4D. Xem [Events](/ipostmap-map/web/v1.0/guides/map-events.md)
