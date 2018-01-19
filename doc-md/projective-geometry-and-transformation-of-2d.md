[TOC]

# Mặt phẳng chiếu 2D
## [Phép chuyển vị của vector](https://vi.wikipedia.org/wiki/Ma_tr%E1%BA%ADn_chuy%E1%BB%83n_v%E1%BB%8B)

- Với một vector ngang (hoặc dọc) $x$ thì vector dọc (hoặc ngang) tương ứng với nó là $x^T$. Cụ thể, một vector ngang $x = (a_1, a_2, ... a_n)$ sẽ có vector dọc tương ứng là $x^T = \begin{pmatrix}
    a_1 \\
    a_2 \\
    \vdots \\
    a_n
\end{pmatrix}$ và ngược lại.
- **Mục đích** của phép chuyển vị là để cho việc nhân vector với matrix được dễ dàng.

- Khi viết $x = (a_1, a_2, ... a_n)$ ta hiểu đây là vector **ngang**.

## Phép nhân vector/matrix:
- Phép nhân matrix: [Tiếng anh](https://en.wikipedia.org/wiki/Matrix_multiplication), [Tiêng việt](https://vi.wikipedia.org/wiki/Ph%C3%A9p_nh%C3%A2n_m%E1%BB%99t_s%E1%BB%91_cho_ma_tr%E1%BA%ADn).
- Phép nhân vô hướng 2 vector: 2 vector cùng chiều $a, b$, thay vì ta viết $a.b$, ta sử dụng kí hiệu **chuyển vị** và chuyển nó thành phép **nhân ma trận** $ab^T$ hoặc $a^Tb$

## Kí hiệu đường thẳng *đồng nhất*:
- Vì mỗi đường thẳng trên mặt phẳng đều có phương trình dạng $ax + by + c = 0$ nên mỗi đường thẳng được chọn bởi bộ 3 số $(a, b, c)$ và ta sẽ đại diện mỗi đường thẳng bằng 1 vector **dọc** $(a, b, c)^T$.
- Vector $(0, 0, 0)^T$ sẽ **không** đại diện cho đường thẳng nào cả.
- Tập hợp các đường thẳng có dạng $(ka, kb, kc)^T$ với $k$ bất kì đều đại diện cho cùng 1 đường thẳng

## Kí hiệu điểm *đồng nhất*:
- Thay vị sử dụng cặp điểm, ta sử dụng vector **ngang** $(x, y, 1)$ để biểu diễn điểm $(x, y)$ trên mặt phẳng.
- **Mục đích** cho việc biểu diễn như vậy để có thể dễ dàng kiểm tra điểm $(x, y, 1)$ có thuộc đường thẳng bằng $l = (a, b, c)^T$ không bằng biểu thức $(x, y, 1).(a, b, c)^T = (ax + by + c) = 0$.
- Mở rộng ra, vector ngang $(x, y, z)$ có thể biểu diễn điểm $\displaystyle \left( \frac{x}{z}, \frac{y}{z} \right)$ trên mặt phẳng toạ độ.

