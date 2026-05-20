# BÀI LÀM — PBT 04

## Câu A1 — 5 Loại Positioning

| Position   | Vẫn chiếm chỗ trong flow? | Tham chiếu vị trí                 | Cuộn theo trang? | Use case                                 |
| ---------- | ------------------------- | --------------------------------- | ---------------- | ---------------------------------------- |
| `static`   | Có                        | Theo flow mặc định                | Có               | Nội dung bình thường                     |
| `relative` | Có                        | Vị trí gốc của chính nó           | Có               | Dịch nhẹ phần tử, làm mốc cho `absolute` |
| `absolute` | Không                     | Nearest positioned ancestor       | Không            | Badge, tooltip, dropdown                 |
| `fixed`    | Không                     | Viewport                          | Không            | Header cố định, nút quay lên đầu trang   |
| `sticky`   | Có                        | Theo flow cho đến khi chạm ngưỡng | Có, rồi dính lại | Sidebar, thanh tiêu đề bảng              |

### Câu hỏi thêm

- `absolute` tham chiếu `body` khi không có ancestor nào có `position` khác `static`.
- `absolute` tham chiếu parent khi parent hoặc ancestor gần nhất có `position: relative`, `absolute`, `fixed` hoặc `sticky`.
- “Nearest positioned ancestor” là ancestor gần nhất tính từ phần tử lên trên có position không phải `static`.

---

## Câu A2 — Flexbox vs Grid

### Trường hợp 1

- `display: flex` + `flex: 1` cho 4 item → 4 item nằm trên 1 hàng, mỗi item chiếm 1/4 chiều ngang container.

### Trường hợp 2

- `flex-wrap: wrap` + `width: 45%` + `margin: 2.5%` cho 6 item → thường sẽ ra 3 hàng, mỗi hàng 2 cột.
- Lý do: mỗi item gần nửa hàng, 2 item vừa đủ 1 hàng.

### Trường hợp 3

- `justify-content: space-between` + `align-items: center` cho 3 item → 3 item nằm trên 1 hàng, item đầu sát trái, item cuối sát phải, item giữa nằm giữa, tất cả căn giữa theo chiều dọc.

### Trường hợp 4

- `grid-template-columns: 200px 1fr 200px` → layout 3 cột: trái 200px, giữa co giãn chiếm phần còn lại, phải 200px.

### Trường hợp 5

- `repeat(3, 1fr)` + 7 item → tạo 3 cột, nên 7 item sẽ thành 3 hàng:
  - Hàng 1: item 1, 2, 3
  - Hàng 2: item 4, 5, 6
  - Hàng 3: item 7 ở cột đầu tiên

---

## PHẦN C — SUY LUẬN

## Câu C1 — Flexbox vs Grid: Khi nào dùng gì?

1. Navigation bar ngang (logo + menu + buttons) → **Flexbox**.
2. Lưới ảnh Instagram (3 cột đều nhau, số ảnh không biết trước) → **Grid**.
3. Layout blog: main content + sidebar → **kết hợp cả hai**.
4. Footer với 4 cột thông tin → **Grid**.
5. Card sản phẩm (ảnh trên, text giữa, nút dưới — nút luôn dính đáy) → **kết hợp cả hai**.

### Giải thích ngắn gọn

- Flexbox hợp cho bố cục 1 chiều, đặc biệt là hàng ngang hoặc cột dọc.
- Grid hợp cho bố cục 2 chiều, có nhiều hàng và cột rõ ràng.
- Với layout phức tạp, dùng kết hợp cả hai là hợp lý nhất.

---

## Câu C2 — Debug Flexbox

### Lỗi 1: Cards không đều chiều cao — nút “Mua” bị nhảy lên/xuống

**Nguyên nhân:** card chưa dùng flex column, nên nút phụ thuộc độ cao nội dung.

**Sửa:**

```css
.card-container {
  display: flex;
  flex-wrap: wrap;
}

.card {
  width: 30%;
  margin: 1.5%;
  display: flex;
  flex-direction: column;
}

.card .btn {
  margin-top: auto;
  padding: 10px;
}
```

### Lỗi 2: Item dính góc trái trên

**Nguyên nhân:** container mới chỉ có `display: flex`, chưa căn giữa ngang và dọc.

**Sửa:**

```css
.hero {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### Lỗi 3: Sidebar bị co lại khi content quá dài

**Nguyên nhân:** sidebar bị co theo mặc định vì `flex-shrink: 1`.

**Sửa:**

```css
.layout {
  display: flex;
}

.sidebar {
  width: 250px;
  flex-shrink: 0;
}

.content {
  flex: 1;
}
```

---

## Ghi chú screenshots

- Chụp screenshot phần kiểm chứng theo yêu cầu của đề.
