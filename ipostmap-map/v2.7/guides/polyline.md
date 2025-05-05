# Polyline

Để vẽ đường thẳng trên bản đồ thì ta sử dụng đối tượng **MFPolyline**. Một đối tượng **MFPolyline** bao gồm một mảng các điểm tọa độ
và tạo ra các đoạn thẳng nối các vị trí đó theo một trình tự có thứ tự.

### Các thuộc tính của **Polyline**:

| Name                   | Type          |Description                                                                                                              |
|------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------|
| **coordinates**        | array[[CoordinateData](#CoordinateData)] | Mảng các tọa độ để tạo ra Polyline. |
| **color**              | string        | Màu sắc của Polyline. Ví dụ: "#00FFFFFF"   |
| **width**              | number        | Độ rộng của **Polyline** theo đơn vị point.                                                                  |
| **lineStyle**          | string        | Quy định kiểu của Polyline là nét liền hay nét đứt. Chỉ dùng **solid** hoặc **dotted**                                |
| **zIndex**             | number        | Chỉ định thứ tự hiển thị giữa các **Polyline** với nhau hoặc giữa **Polyline** với các đối tượng khác trên bản đồ. Giá trị mặc định là **0**.  |
| **visible**            | bool          | Xác định **Polyline** có thể ẩn hay hiện trên bản đồ. Giá trị mặc định là **true**.                                       |
| **userData**           | object        | Dữ liệu bất kỳ mà người dùng muốn lưu cùng với **Polyline**.                                       |
| [onPress](#onPress) | func   | Callbacks để nhận sự kiện khi người dùng press **Polyline** trên map.                                                                          |

### Thêm một Polyline

![Polyline](../../resources/polyline.png)

```javascript
render() {
  <MFMapView ref={ref => this.map = ref} >
    <MFPolyline ref={ref => this.polyline = ref}
      coordinates={[
        { longitude: 106.69870376586914, latitude: 10.787569188027405 },
        { longitude: 106.69998586177826, latitude: 10.787247741194244 },
        { longitude: 106.70092999935150, latitude: 10.78798548751378 }
      ]}
      lineStyle="solid"
      width={15}
      color="#00FFFFFF"
      onPress={(event) => {console.log('on press circle:', event.nativeEvent)}}
      zIndex={4.0}
      userData={{name: "First Polyline", id: 10}}
      visible={true}
    />
  </MFMapView>
}
```

### Methods

| Name                   | Parameters                           | Description                                                                            |
|------------------------|:------------------------------------:|------------------------------------------------------------------------|
| **setCoordinates**     | array[[CoordinateData](#CoordinateData)] | Set mảng tọa độ cho Polyline                                    |
| **setWidth**           | number                               | Set độ rộng cho polyline.                                              |
| **setColor**           | string                               | Set màu cho polyline. Ví dụ: "#00FFFF7F"                               |
| **setVisible**         | bool                                 | Ẩn/hiện polyline trên map                                              |
| **setZIndex**          | number                               | Set giá trị zIndex cho polyline                                        |
| **setLineStyle**       | string                               | Set kiểu vẽ của polyline (**solid** hoặc **dotted**)                   |
| **setUserData**        | object                               | Set dữ liệu bất kỳ cho polyline                                        |

### Object Types

#### CoordinateData

Thông tin tọa độ theo kinh độ, vĩ độ

```js
let coordinate = {latitude: 10.7881732, longitude: 106.7000933}
```

### Events

#### onPress

Được gọi khi người dùng tap vào `polyline` trên bản đồ.  
Giá trị `nativeEvent` trả về của đối tượng event khi sự kiện `onPress` được gọi là một object, có dạng như sau:

```js
{
  action: "polyline-press",
  location: {
    latitude: number,
    longitude: number
  },
  pixel: {
    x: number,
    y: number
  },
  polyline: {
    userData: object
  }
}
```

Trong đó:
  - location: vị trí mà người dùng tap trên bản đồ, theo hệ tọa độ địa lý.
  - pixel: vị trí mà người dùng tap trên bản đồ, theo hệ tọa độ màn hình.
  - polyline: thông tin trả về cho polyline, bao gồm:
    + userData: object chứa thông tin được set vào thông qua props `userData`.
