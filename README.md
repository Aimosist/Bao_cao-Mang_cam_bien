Đo nhiệt độ, độ ẩm, ánh sáng bằng ESP8266 gửi tin nhắn bằng MQTT qua Node.js để tạo data MySQL rồi hiển thị số đo, bảng và điều khiển LED trên Web 

Mô tả:

Bài tập này sử dụng ESP8266 để đo nhiệt độ, độ ẩm và cường độ ánh sáng, phát số liệu bằng tin nhắn qua Mosquitto MQTT cho Node.js xử lý, sau đó gửi dữ liệu lên MySQL. 
Thiết bị cảm biến kết nối với ESP8266 sẽ liên tục thu thập dữ liệu và cập nhật dữ liệu để hiển thị các thông tin, bảng biểu kết hợp điều khiển Led của ESP8266 thông qua một web tạo ra từ Node.js.

Thành phần sử dụng:

* ESP8266: giao tiếp với cảm biến và gửi số liệu các cảm biến cho Mosquitto MQTT.
* Mosquitto MQTT: tạo tin nhắn để gửi cho Node.js từ số liệu các cảm biến, hỗ trợ giao tiếp qua MQTT.
* Node.js: xử lý tin nhắn MQTT thành dữ liệu nhiệt độ, độ ẩm, ánh sáng,... để lưu trữ trên MySQL; tạo web từ các code html để hiển thị, vẽ bảng các data và điều khiển Led.
* MySQL: lưu trữ thông tin nhiệt độ, độ ẩm,... ; vẽ bảng, hiển thị lịch sử data của cảm biến, lịch sử bật tắt Led;...
* Cảm biến nhiệt độ (DHT11): Đo nhiệt độ và độ ẩm.
* Cảm biến ánh sáng: Đo cường độ ánh sáng.
* Các điện trở 1k ôm.
* Dây breadboard.
* Breadboard.
* Nguồn cấp: Micro USB.
* Các code js, html.
  
Phần mềm:
* Arduino IDE: lập trình và nạp code cho ESP8266.
* Notepad: đổi đuôi .txt thành .html, .js để tạo code cho Node.js.
* Trình duyệt web để chạy.

Kết nối mạch:
* DHT 11:
* Chân VCC nối với 3.3V.
* Chân GND nối với GND.
* Chân Data nối với chân D2 của ESP8266.
  
* Cảm biến ánh sáng:
* Chân VCC nối với 3.3V.
* Chân GND nối với GND.
* Chân A0 nối với chân A0 của ESP8266.
* Chân D0 nối với chân D1 của ESP8266 (chưa sử dụng).

Cài đặt:
1. Cài đặt Arduino IDE và thêm board ESP8266.
2. Cài đặt các thư viện cần thiết: DHT Sensor Library, Adafruit Sensor Library, ESP8266WiFi, ESP8266WebServer.
3. Kết nối ESP8266 với máy tính qua cổng USB, chọn board ESP8266.
4. Nạp code cho ESP8266.
Cấu hình WIFI và MQTT
        Cấu hình lại Wifi cho phù hợp.
                const char* ssid = "Tên WiFi";
				const char* password = "Mật Khẩu WiFi";
				const char* mqtt_server = "Địa chỉ IP";
        Thay đổi user, password và port.
Hiển thị dữ liệu trên web
1. Ghi dữ liệu được gửi từ ESP vào database: sử dụng code để ghi dữ liệu (getdata.py).
2. Giao diện web:
* Cấu trúc thư mục mẫu:

* Khởi chạy file code get_data.py để cập nhật dữ liệu trang web liên tục. Sau khi chạy, mở địa chỉ có trong terminal để mở giao diện trang web.
