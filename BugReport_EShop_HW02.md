# Bug Report — EShop (HW02 Domain Testing)

> Điền 1 mục cho mỗi bug tìm được. Nhớ đăng đồng thời lên GitHub Issues của nhóm (kèm ảnh chụp màn hình) theo yêu cầu đề bài.

---

## Tổng quan

| # | Feature (FR-xx) | Title | Severity | Trạng thái |
|---|---|---|---|---|
| BUG-01 | FR-06 | Không trả về lỗi khi không truyền id | Minor | Open |
| BUG-02 | FR-06 | Nhấn nút thêm vào giỏ hàng phải double click, nhấn một lần không nhận | Critical | Open |
| BUG-03 | FR-06 | Thêm vào giỏ thành công sản phẩm với số lượng 0 | Critical | Open |
| BUG-04 | FR-06 | Thêm vào giỏ thành công sản phẩm với số lượng -5 | Critical | Open |
| BUG-05 | FR-06 | Nhập số lượng là 1.5 và thêm vào giỏ thành công với số lượng 1 | Critical | Open |
| BUG-06 | FR-06 | Để trống ô số lượng và thêm vào giỏ thành công | Critical | Open |
---

## BUG-01

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:** Không trả về lỗi khi không truyền id (http://localhost:5173/product/)
- **Severity:** Minor
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-A6 
- **Môi trường:** Trình duyệt web

**Steps to reproduce:**
1. Để id rỗng khi gọi `GET /api/products/`

**Input test:**
| Biến | Giá trị |
|---|---|
| id| |

**Expected result:**
> Trả về lỗi

**Actual result:**
> Không trả về lỗi

**Screenshot:**
> ![BUG-01](reference/BUG-01.png)


---

## BUG-02

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:** Nhấn nút thêm vào giỏ hàng phải double click, nhấn một lần không nhận
- **Severity:** Critical
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-B1
- **Môi trường:** Trình duyệt Web

**Steps to reproduce:**
1. Đăng nhập với quyền User Test
2. Nhấn vào trang chi tiết sản phẩm
3. Nhấn nút thêm vào giỏ hàng

**Input test:**
| Biến | Giá trị |
|---|---|
| Nút thêm vào giỏ hàng | |

**Expected result:**
> Nhấn một lần phải thêm ngay

**Actual result:**
> Phải nhấn double-click mới thêm

**Screenshot:**
> ![BUG-02](reference/BUG-02.png)


---

## BUG-03

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:** Thêm vào giỏ thành công sản phẩm với số lượng 0
- **Severity:** Critical
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-B2
- **Môi trường:** Trình duyệt Web

**Steps to reproduce:**
1. Đăng nhập với quyền User Test
2. Nhấn vào trang chi tiết sản phẩm
3. Chọn số lượng là 0
4. Nhấn nút thêm vào giỏ hàng
5. Sản phẩm vẫn được thêm vào giỏ

**Input test:**
| Biến | Giá trị |
|---|---|
| Quantity |0|

**Expected result:**
> Không cho thêm vào giỏ, thông báo lỗi

**Actual result:**
> Sản phẩm được thêm vào giỏ

**Screenshot:**
> ![BUG-03](reference/BUG-03.png)

---

## BUG-04

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:** Thêm vào giỏ thành công sản phẩm với số lượng -5
- **Severity:** Critical
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-B2b
- **Môi trường:** Trình duyệt Web

**Steps to reproduce:**
1. Đăng nhập với quyền User Test
2. Nhấn vào trang chi tiết sản phẩm
3. Chọn số lượng là -5
4. Nhấn nút thêm vào giỏ hàng
5. Sản phẩm vẫn được thêm vào giỏ

**Input test:**
| Biến | Giá trị |
|---|---|
| Quantity |-5|

**Expected result:**
> Không cho thêm vào giỏ, thông báo lỗi

**Actual result:**
> Sản phẩm được thêm vào giỏ

**Screenshot:**
> ![BUG-04](reference/BUG-04.png)

---

## BUG-05

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:** Nhập số lượng là 1.5 và thêm vào giỏ thành công với số lượng 1
- **Severity:** Critical
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-B3
- **Môi trường:** Trình duyệt Web

**Steps to reproduce:**
1. Đăng nhập với quyền User Test
2. Nhấn vào trang chi tiết sản phẩm
3. Chọn số lượng là 1.5
4. Nhấn nút thêm vào giỏ hàng
5. Sản phẩm vẫn được thêm vào giỏ với quantity là 1

**Input test:**
| Biến | Giá trị |
|---|---|
| Quantity |1.5|

**Expected result:**
> Không cho thêm vào giỏ, thông báo lỗi

**Actual result:**
> Sản phẩm được thêm vào giỏ với quantity là 1

**Screenshot:**
> ![BUG-05](reference/BUG-05a.png)
> ![BUG-05](reference/BUG-05b.png)

---

## BUG-06

- **Feature:** FR-06 — Xem chi tiết sản phẩm (Product Detail View)
- **Title:**  Để trống ô số lượng và thêm vào giỏ thành công
- **Severity:** Critical
- **Kỹ thuật phát hiện:** Domain Testing
- **Test case liên quan:** TC-B5
- **Môi trường:** Trình duyệt Web

**Steps to reproduce:**
1. Đăng nhập với quyền User Test
2. Nhấn vào trang chi tiết sản phẩm
3. Để trống ô số lượng
4. Nhấn nút thêm vào giỏ hàng
5. Sản phẩm vẫn được thêm vào giỏ

**Input test:**
| Biến | Giá trị |
|---|---|
| Quantity ||

**Expected result:**
> Không cho thêm vào giỏ, thông báo lỗi

**Actual result:**
> Sản phẩm được thêm vào giỏ

**Screenshot:**
> ![BUG-06](reference/BUG-06.png)

---

## Ví dụ đã điền (tham khảo cách viết)

## BUG-EX

- **Feature:** FR-15 — Quản lý sản phẩm (CRUD)
- **Title:** Hệ thống vẫn tạo được sản phẩm khi giá = 0
- **Severity:** Major
- **Kỹ thuật phát hiện:** Boundary Value Analysis (boundary `price > 0`, giá trị ON = 0)
- **Test case liên quan:** TC-BVA-03
- **Môi trường:** Chrome 126, tài khoản admin@eshop.test

**Steps to reproduce:**
1. Đăng nhập với quyền Admin.
2. Vào trang Quản lý sản phẩm → Thêm sản phẩm mới.
3. Nhập Tên = "Test Product", Giá = 0, Danh mục hợp lệ.
4. Nhấn Lưu.

**Input test:**
| Biến | Giá trị |
|---|---|
| Tên | Test Product |
| Giá | 0 |
| Danh mục | Đồ điện tử |

**Expected result:**
> Hệ thống từ chối và hiển thị thông báo lỗi "Giá phải lớn hơn 0" (theo ràng buộc `price > 0` trong đặc tả).

**Actual result:**
> Sản phẩm được tạo thành công với giá = 0, hiển thị bình thường trên trang danh sách sản phẩm.

**Screenshot / Video:**
> screenshots/bug-ex-price-zero.png

**GitHub Issue:** https://github.com/<org>/eshop-sut/issues/1
