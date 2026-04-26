
A1
Các cách nhúng CSS vào HTML là:
+ Inline:
  ```html
    <h1 style="background-color:red"></h1>
  ```
+ Internal
  ```html
    <style>
      p{
        background-color: red;
      }
    </style>
  ```
+ External
    ```html
    <link rel="stylesheet" href="mystyle.css">
    ```

+ Nếu có 3 loại nhúng CSS cùng được dùng thì loại nào viết sau sẽ ghi đè loại được viết trước, vì code được dịch từ trên xuống.

A2
```css
1. h1                           → Chọn: <h1l>ShopTLU</h1> 
2. .price                       → Chọn: <p class="price">25.990.000</p>
3. #app header                  → Chọn: <header class="top-bar dark"></header>
4. nav a:first-child             → Chọn: `<a href="/" class="active">Home</a>`
5. .product.featured h2         → Chọn: `<h2>MacBook Pro</h2>`
6. article > p                  → Chọn: `<p class="price">25.990.000đ</p>
            <p>Mô tả sản phẩm...</p>`
7. a[href="/"]                  → Chọn: <a href="/" class="active">Home</a
8. .top-bar.dark h1              → Chọn:  <h1>ShopTLU</h1>
```

A3