# Viettel-Virtualization-Course
## Challenge 1
#### Mục tiêu

Triển khai một `Deployment` chạy `nginx` trên Kubernetes và cấu hình để có thể truy cập từ bên ngoài thông qua `NodePort`.

#### Yêu cầu

- Tạo một `Deployment` có tên là `nginx-deployment` với 2 replicas, mỗi replica chạy một container `nginx`.
- Tạo một `Service` kiểu `NodePort` trỏ đến `Deployment` này, cho phép truy cập từ bên ngoài qua `NodePort`.
- Kiểm tra kết quả triển khai bằng cách thực hiện `curl` đến địa chỉ `NodeIP:NodePort` để truy cập trang web mặc định của `nginx`.
##### - Phân tích:
![Mô tả hình ảnh](images/Challenge%201/diagram_1.png)
##### - Hướng dẫn triển khai:
1. **Tạo file `nginx-deployment.yaml`**: Định nghĩa `Deployment` cho `nginx` với 2 replicas.
2. **Tạo file `nginx-service.yaml`**: Định nghĩa `Service` kiểu `NodePort` trỏ đến `nginx-deployment`.
3. **Triển khai các tệp cấu hình**:
   ```bash
   kubectl apply -f nginx-deployment.yaml
   kubectl apply -f nginx-service.yaml
4. **Thực hiện `curl` đến `http://<NodeIP>:<NodePort>` để kiểm tra trang web mặc định của `nginx`**

##### - Kết quả:
![Mô tả hình ảnh](images/Challenge%201/code_1.png)
![Mô tả hình ảnh](images/Challenge%201/result_1.png)
## Challenge 2

#### Mục Tiêu
Triển Khai Ứng Dụng Web Tĩnh lên Kubernetes
#### Yêu cầu
- Đóng gói thành công container chứa ứng dụng web tĩnh.
- Tạo một `Deployment` chạy ứng dụng web tĩnh với 2 replicas.
- Tạo một `NodePort Service` để truy cập ứng dụng từ bên ngoài.
- Kiểm tra truy cập ứng dụng qua `curl` với `NodePort` và xác nhận kết quả trang web tĩnh.

##### - Phân tích:
![Mô tả hình ảnh](images/Challenge%202/diagram_2.png)
##### - Hướng dẫn triển khai:
1. **Đóng Gói Container Web Tĩnh**
- Tải một template web tĩnh từ [Free CSS Templates](https://www.free-css.com/free-css-templates).
- Sử dụng base image là `nginx` để phục vụ các file web tĩnh.
- Cấu hình nginx trỏ tới các file web tĩnh.
  - Tham khảo một ví dụ cấu hình nginx đơn giản tại: [nginx configuration example](https://gist.github.com/mockra/9062657).

2. **Triển Khai Deployment**
- Tạo một `Deployment` với 2 replicas, chạy ứng dụng web tĩnh.
  
3. **Tạo NodePort Service**
- Tạo một `Service` với loại `NodePort` để truy cập ứng dụng từ bên ngoài.

4. **Kiểm Tra Kết Quả**
- Thực hiện lệnh `curl` tới `NodePort` để kiểm tra xem ứng dụng web tĩnh có hoạt động và hiển thị đúng trang web không.
##### - Kết quả:
![Mô tả hình ảnh](images/Challenge%202/code_2.png)
![Mô tả hình ảnh](images/Challenge%202/result_2.png)


