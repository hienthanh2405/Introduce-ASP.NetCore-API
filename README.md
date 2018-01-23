# Introduce-ASP.NetCore-API
This is a project to introduce ASP.Net Core for Web API
# Cách sử dụng POSTMAN
## Biến môi trường trong POSTMAN
  - POSTMAN có 3 môi trường local, staging và production, mỗi môi trường sẽ có 1 `base_url` riêng biệt.
  - POSTMAN cung cấp cho chúng ta tùy chọn Environments Variable (biến môi trường). Các biến môi trường sẽ được sử dụng mọi nơi trong     url, header, body, ...
  - Environments variable (biến môi trường)cho phép ta cài đặt các biến môi trường, sau đó trong mỗi môi trường ta có thể lấy biến đó ra   với nội dung riêng biệt.
  - Ví dụ :
      + Bước 1 : Tạo 2 Môi trường Local và Staging trên Postman.<br> 
      ![](https://viblo.asia/uploads/3ca463cf-3a4f-4093-a89c-7a389b344dfc.png)
      + Bước 2 : Tạo 2 biến `base_url` cho 2 môi trường `local`,  `staging` để thuận lợi khi dùng ở mỗi môi trường. <br>
        + Staging: base_url = http://bobo.com
        + Local: base_url = http://localhost:3000  
      ![](https://viblo.asia/uploads/099468e6-b84a-46c8-aa7f-9fad968e6e8e.png) 
      ![](https://viblo.asia/uploads/25c41a74-3ea5-4369-bca3-40754a912a6c.png) 
     
      + Bước 3 : Sau đó, trong link gọi Web API, ta chỉ việc gọi biến base_url và đặt nó trong ngoặc nhọn {{}} là xong.<br><br>
      ![](https://viblo.asia/uploads/04d7d173-27ec-4735-8e47-2c28249057f0.png) <br> 
      + Bước 4 : Bây giờ mỗi khi muốn test trên từng môi trường, chỉ cẩn chuyển đổi qua lại các môi trường. <br> <br>
      ![](https://viblo.asia/uploads/2a4c54fa-a080-4c20-be40-db8186025507.png) <br> 
     
  ==> `Ưu điểm sử dụng biến môi trường :`<br>
      + Khi không dùng biến môi trường (Environments Variable) thì khi bạn cần test trên từng môi trường (local, staging và production),
      bạn phải tạo ra 3 `request` với thông số giống hệt nhau, chỉ khác mỗi base_url ==> gây một số bất tiện khi test API.<br>
      + khi đó sử dụng Environments Variable , thì bạn chỉ cần chuyển đổi qua lại các môi trường mà không cần phải thay đổi đường dẫn         url hoặc bất kì chỗ nào khác nếu bạn có sử dụng biến.<br>
 
 ## Biến sẵn có của POSTMAN


## Export trong POSTMAN
  - Export: Dùng để share Collection với các thành viên khác trong team , ta có thể export nó ra file json sau đấy gửi cho member khác     và họ có thể import vào và dùng luôn trực tiếp được. 
  - Share Colection :Có chức năng tương tự Export, Share Collection dưới dạng link online, với link này ta có thể gửi cho team member và   người đó có thể dùng Postman để mở nó.
  + Bước 1 : Click vào Collection cần export => Click Export Collection đó .<br>
  ![](https://i.imgur.com/ovGVUhM.png)
  + Bước 2 : Chọn Collection . Click `export` . Sau đó chọn đường dẫn, nơi lưu file .Json của việc Export. Khi ta click vào Export và nó   sẽ tạo ra 1 file .json, sau đấy gửi file json đấy cho member khác dùng để import.<br>
  ![](https://i.imgur.com/mwnQyLm.png)<br>
  
## Import trong POSTMAN
  - Import : Dùng để truyền file `.json` từ việc Export khi chia sẻ  Collection vào Postman. 
  - Bước 1 : Click `Import` trên thanh `mennu bar` hoặc click `file` --> chọn `Import`.<br>
  ![](https://i.imgur.com/QOqyQ44.png)
  - Bước 2 : Click `Choose files` chọn file `.json `từ máy để Import. <br>
  ![](https://i.imgur.com/KTDB8uU.png)
  - Bước 3 : Chọn file `.json` xong ta sẽ được nó Import vào main của POSTMAN.<br>
  
# Controller trong ASP.NET của web API
  - Bộ điều khiển (Controller) là một đối tượng xử lý các yêu cầu HTTP và tạo ra phản hồi HTTP trả về kết quả các file .JSON hoặc XML.
  - Với ASP.NET Web API, các phương thức controller chỉ cần trả về dữ liệu gốc, toàn bộ phần còn lại sẽ tự động được chuyển đổi sang       JSON hay XML tùy theo yêu cầu từ gọi tới. Nhưng với MVC, để cho phép các phương thức controller trả về dữ liệu JSON hay XML thì phải     tùy biến kết quả trả về ở dạng nguyên gốc. 
  - Các action HTTP (như GET, POST) tự động gắn kết vào các phương thức của controller (chính là các controller action) thông qua tên     của chúng. Ví dụ :<br>
  ![](http://itprotraining.vn/files/article_upload/images/articles/2015/10/webapi_01/auto_mapped_crud_actions.png)
  - Tạo thêm 1 Controller:
    + Bước 1 : Sau khi tạo Project , trong Solution Explorer, click phải vào thư mục Controllers, chọn Add > New Item. Trong Add New         Item, chọn Web API Controller Class, đặt tên cho class , khi đó file sẽ có đuôi `.controller` theo đúng quy tắc chuẩn.<br>
    ![](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api/_static/new_controller.png)
    + Bước 2 : khi đó file mới được tạo ra sẽ có sẵn code như sau :<br>
    ![](https://i.imgur.com/32UmwaY.png)
    + Bước 3 : Thêm các phương thức như : get, post, put, ... vào controller vừa tạo. Khi sử dụng chúng ta chỉ cần theo đường dẫn URL       trong Class Controller của nó (ví dụ : Route"api/[controller]") để dẫn vào các phương thức này.
    

# Chức năng của file STARTUP.CS
  - Sử dụng file Startup.cs để ứng dụng của bạn có thể đọc dữ liệu cấu hình cần thiết một cách tự động. 
  - File Startup.cs bao gồm :
      - Phương phức `ConfigureServices` để cấu hình các dịch vụ của ứng dụng.
      - Phương phức `Configure` Cấu hình để tạo đường ống xử lý yêu cầu ứng dụng.<br>
      --> 2 phương thức này sẽ được tự động thực hiện khi ứng dụng của bạn bắt đầu chạy.<br>
      ![](https://i.imgur.com/FYZtJhz.png)<br>
      - Phương phức `ConfigureServices` được gọi bởi máy chủ (web host) , trước các phương thức `Configure`.
      - Các phương phức `Configure` được sử dụng để xác định cách ứng dụng đáp ứng các yêu cầu HTTP. 
      
  - Startup.cs file đặc trưng giống như thế này:<br>

     ` public partial class Startup {`<br>
          `public Startup(IHostingEnvironment env)`<br>
          `{`<br>
          `Configuration = new Configuration()`<br>
          `.AddJsonFile("config.json")`<br>
          `.AddEnvironmentalVariables();`<br>
          `}`<br>
      `}`<br>
  - Đoạn lập trình trên minh họa cách bạn có thể thiết lập ứng dụng để có thể đọc được dữ liệu cấu hình từ file .JSON . 
  - Startup.cs file giúp thêm hay loại bỏ các configuration source (code để cấu hình) dễ dàng dành cho ứng dụng của bạn.


  
  
      
