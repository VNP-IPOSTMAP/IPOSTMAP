# Projection

Lớp [Projection](/ipostmap-map/web/v1.0/reference/map.md?id=projection-class) được dùng để chuyển đổi giữa vị trí trên màn hình và tọa độ địa lý trên bề mặt trái đất và ngược lại.

## 1. Khởi tạo lớp Projection
```javascript
let projection = new map4d.Projection(map)
```

## 2. Chuyển đổi từ toạ độ LatLng sang toạ độ Screen

```javascript
let screenCoordinate = projection.fromLatLngToScreen(new LatLng(10.771783, 106.700763))
```

## 3. Chuyển đổi từ toạ độ LatLng sang toạ độ Screen với elevation (meter)

```javascript
let target = new LatLng(10.771783, 106.700763)
let elevation = 10
let screenCoordinate = projection.fromLatLngToScreen(target, elevation)
```

## 4. Chuyển đổi từ toạ độ Screen sang toạ độ LatLng

```javascript
let latLngCoordinate = projection.fromScreenToLatLng({x: 100, y: 100})
```

## 5. Chuyển đổi từ toạ độ Screen sang toạ độ LatLng với elevation (meter)

```javascript
let screenCoordinate = {x: 100, y: 100}
let elevation = 20
let latLngCoordinate = projection.fromScreenToLatLng(screenCoordinate, elevation)
```

## 6. Chuyển đổi tọa độ từ tọa độ LatLng sang tọa độ thế giới

```javascript
let point = projection.fromLatLngToPoint(new LatLng(10.771783, 106.700763))
```

## 7. Chuyển đổi từ tọa độ thế giới sang tọa độ LatLng

```javascript
let latlng = projection.fromPointToLatLng({x: 100, y: 100})
```
