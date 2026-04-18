Câu A1  
a)Các bước xảy ra gồm:

1. Request đi từ laptop đến router tại nhà
2. Sau đó đi qua IPS
   3.chạy đến server của shoppe thông qua cáp quang
   4.Server xử lý request hiển thị lên Homepage
   5.Sau đó repsonse được Server gửi ngược lại laptop
   6.Trình duyệt nhận tập file HTML, CSS, JS sau đó render ra giao diện Homepage

b) Tab network trong devtool của Chrome cho ta thấy:

- Danh sách các request
- Chi tiết các thông tin của 1 request
- Các tài nguyên được gửi về (CSS,JS, IMG, FONT, etc)

![Ảnh màn hình thông tin của tab network](image.png)

Câu A2
Các lỗi semantic là:
Trang web bị GG đánh lỗi SEO thấp do, mắc phải các lỗi semantic, dùng các thẻ chưa đúng và chưa hợp lý, khiến cho trang web không được đánh giá cao.

Các lỗi semantic trong trang web là
1. Title của sản phẩm lại dùng thẻ div ```<div>```, thay vào đó nên dùng thẻ heading để làm nổi bật tên sản phẩm
   ```html
   <div class="title">iPhone 16 Pro</div>
   ```
   sửa
   ```html
   <h2 class="title">iPhone 16 Pro</h2>
   ```
2. Khung bao bọc phần quan trọng nhất của trang web (sản phẩm) lại được bọc trong thẻ div với class là main```<div class="main">```, nên dùng thẻ main để trình duyệt biết dược đây là phần quan trọng nhất của trang web để tối ưu semantic
   ```html
   <div class=main>...</div>
   ```
   sửa
   ```html
   <main>...</main>
   ```

3. Thay vì bao bọc sản phẩm(product) bằng một thẻ div```<div class="product">```, ta thấy mỗi sản phẩm có thể là một nội dung riêng biệt, nên có thể dùng thẻ article để tối ưu.
   ```html
   <div class="product">...</div>
   ```
   sửa
   ```html
   <article class="title">...</article>
   ```

4. Ở phần giá tiền, ta thấy trang web đang dùng thẻ ```<div class="price">```, nhưng thực tế giá tiền đó là một giá trị vậy để tối ưu ta có thể dùng thẻ data để hiển thị.
   ```html
   <div class="price">25.990.000đ</div>
   ```
   sửa
   ```html
   <data value="2599000">25.990.000đ</data>
   ```

Câu A3
Kết quả hiển thị
<pre>
--------------------------------
|Hộp 1                         |
|Text A Text B                 |
|Hộp 2                         |
|Text C <strong>Text D</strong>                 |
|Hộp 3                         |
|                              |
|                              |
|                              |
--------------------------------
</pre>
 Giải thích
 + đối với các thẻ như ```<div>``` thì render ra trên browser text trong các thẻ sẽ xuống dòng vì vậy các nội dung như Hộp 1, Hộp 2 và Hộp 3 mới ở mỗi cái một dòng, tương tự với nội dung được bao bọng trong các thẻ đó

+ đối với các thẻ như ```<span>``` thì thẻ này hoàn toàn có thể render trên cùng 1 dòng với các thẻ nội dung khác như vì vậy các nội dung như "Text A", "Text B" mới có thể đứng cùng 1 dòng

+ đối với thẻ ```<strong>``` thẻ này render tương tự như thẻ ```<span>``` có thể ở cùng dòng với các nội dung khác nhưng thẻ này có nhiệm vụ in đậm text bên trong và nói cho browser biết đây là nội dung cần được chú ý.