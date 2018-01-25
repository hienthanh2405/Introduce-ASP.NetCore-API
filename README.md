# Introduce-ASP.NetCore-API
This is a project to introduce ASP.Net Core for Web API

<h1> Routing và cách đặt tên route.</h1>

Trong ASP.NET Web API, controller là một class chịu trách nhiệm xử lý HTTP requests. Những public method của controller được gọi là action methods hay actions. Khi framework Web API nhận một request, nó truyền request đó đến một action.Để xác định action nào sẽ được gọi, framework sử dụng một cấu trúc gọi là routing table. Routing table được cấu hình trong file WebApiConfig.cs nằm trong thư mục App_Start của project<br>

![](https://i.imgur.com/URNofch.jpg)<br>

Cơ chế routing mặc định của ASP.NET Web API có thể được customize. Nếu không muốn sử dụng quy ước đặt tên các action dựa trên tên của HTTP methods, chúng ta có thể mô tả tường minh action nào sẽ map với HTTP method nào bằng cách sử dụng các attribute HttpGetAttribute, HttpPostAttribute, HttpPutAttribute, và HttpDeleteAttribute.
Trong ví dụ dưới đây, method FindProduct được map tới GET request
public class ProductController : ApiController<br>

![](https://i.imgur.com/M3gC9hZ.jpg)<br>

Với route template mặc định, Web API sử dụng HTTP methods để xác định action. Nếu muốn thay đổi URI của HTTP request, chúng ta có thể thêm vào các route ngoài route mặc định như ví dụ sau<br>

![](https://i.imgur.com/d9ckNez.jpg)<br>

