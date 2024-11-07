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
![Mô tả hình ảnh](images/Challenge%201/code_1.jpg)
![Mô tả hình ảnh](images/Challenge%201/result_1.jpg)
## Challenge 2
![Mô tả hình ảnh](images/Challenge%202/diagram_2.png)
![Mô tả hình ảnh](images/Challenge%202/code_2.png)
![Mô tả hình ảnh](images/Challenge%202/result_2.png)


