# Introduce-ASP.NetCore-API
This is a project to introduce ASP.Net Core for Web API
# Cách sử dụng POSTMAN
## Biến môi trường trong POSTMAN
  - POSTMAN có 3 môi trường local, staging và production, mỗi môi trường sẽ có 1 `base_url` riêng biệt.
  - POSTMAN cung cấp cho chúng ta tùy chọn Environments Variable (biến môi trường). Các biến môi trường sẽ được sử dụng mọi nơi trong url,    header, body, ...
  - Environments variable (biến môi trường)cho phép ta cài đặt các biến môi trường, sau đó trong mỗi môi trường ta có thể lấy biến đó ra      với nội dung riêng biệt.
  - Ví dụ :
      + Bước 1 : Tạo 2 Môi trường Local và Staging trên Postman.<br>
      ![](https://viblo.asia/uploads/3ca463cf-3a4f-4093-a89c-7a389b344dfc.png)<br>
      + Bước 2 : Tạo 2 biến `base_url` cho 2 môi trường `local`,  `staging` để thuận lợi khi dùng ở mỗi môi trường.
        + Staging: base_url = http://bobo.com
        + Local: base_url = http://localhost:3000 <br>
      ![](https://viblo.asia/uploads/099468e6-b84a-46c8-aa7f-9fad968e6e8e.png) <br>
      ![](https://viblo.asia/uploads/25c41a74-3ea5-4369-bca3-40754a912a6c.png) <br>
      + Bước 3 : Sau đó, trong link gọi Web API, ta chỉ việc gọi biến base_url và đặt nó trong ngoặc nhọn {{}} là xong.<br>
      ![](https://viblo.asia/uploads/04d7d173-27ec-4735-8e47-2c28249057f0.png) <br>
      + Bước 4 : Bây giờ mỗi khi muốn test trên từng môi trường, chỉ cẩn chuyển đổi qua lại các môi trường. <br>
      ![](https://viblo.asia/uploads/2a4c54fa-a080-4c20-be40-db8186025507.png) <br>
      
  ==> `Ưu điểm sử dụng biến môi trường :`<br>
      + Khi không dùng biến môi trường (Environments Variable) thì khi bạn cần test trên từng môi trường (local, staging và production),
      bạn phải tạo ra 3 `request` với thông số giống hệt nhau, chỉ khác mỗi base_url ==> gây một số bất tiện khi test API.<br>
      + khi đó sử dụng Environments Variable , thì bạn chỉ cần chuyển đổi qua lại các môi trường mà không cần phải thay đổi đường dẫn url       hoặc bất kì chỗ nào khác nếu bạn có sử dụng biến.<br>
      
## Biến sẵn có của POSTMAN
## Import trong POSTMAN
## Export trong POSTMAN
  - Export: Dùng để share Collection với các thành viên khác trong team , ta có thể export nó ra file json sau đấy gửi cho member khác và   họ có thể import vào và dùng luôn trực tiếp được. 
  - Share Colection :Có chức năng tương tự Export, Share Collection dưới dạng link online, với link này ta có thể gửi cho team member và     người đó có thể dùng Postman để mở nó.
      
