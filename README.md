# AI_Challenge_2022
"Truy vấn sự kiện từ dữ liệu thị giác (Event Retrieval from Visual Data)."</br>
1.Hướng dẫn dự thi: các đội vui lòng xem file [tại đây](https://drive.google.com/file/d/1IWwP-9eXhGFcbndfvxfTWkqIEA_waY_V/view).

2.Dữ liệu mẫu:

Dữ liệu cung cấp cho các đội thi để làm quen với bài toán với khoảng 100 giờ gồm 300 video với các thông tin đi kèm tương ứng như sau:

* Videos: Chứa video được cung cấp
* Keyframes: Chứa tất cả keyframe được trích xuất từ video được cung cấp ở trên, tên của file keyframe tương ứng với vị trí của keyframe đó trong video. Keyframe sẽ được lưu trong thư mục tương ứng với tên file video, ví dụ: các keyframe của video C00_V0000.mp4 sẽ được lưu trong thư mục C00_V0000 
* Objects: Chứa json tất cả vật thể (object) phát hiện được từ mô hình [Faster RCNN pretrained OpenImagesV4](https://tfhub.dev/google/faster_rcnn/openimages_v4/inception_resnet_v2/1). Chi tiết kết quả từ mô hình phát hiện vật thể có thể xem ví dụ tại đây https://www.tensorflow.org/hub/tutorials/object_detection. Tên file json chứa danh sách các objects tương ứng với tên file keyframe, ví dụ keyframe C00_V0000/000000.jpg sẽ có file json chứa thông tin các object là C00_V0000/000000.json
* CLIP features: Chứa thông tin CLIP features của tất cả các frames trong thư mục Keyframes. Tất cả các CLIP features của các keyframe sẽ được lưu thành một file npy duy nhất, với thứ tự của các vector features tăng dần ứng với chỉ số của keyframes. Ví dụ video C00_V0000 có 252 keyframe (gồm: 000000,000096,...) được lưu trong file C00_V0000.npy với vector đầu tiên ứng với CLIP features của keyframe 000000, vector tiếp theo ứng với CLIP features của keyframe 000096,...
