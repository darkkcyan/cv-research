# Hình học xạ ảnh và phép biến đổi 2D
[TOC]
-----------------------------------

## The 2D projective plan - Mặt phẳng xạ ảnh 2D
### [Phép chuyển vị của vector/matrix](https://vi.wikipedia.org/wiki/Ma_tr%E1%BA%ADn_chuy%E1%BB%83n_v%E1%BB%8B)

- Với một vector ngang (hoặc dọc) $x$ thì vector dọc (hoặc ngang) tương ứng với nó là $x^T$. Cụ thể, một vector ngang $x = (a_1, a_2, ... a_n)$ sẽ có vector dọc tương ứng là $x^T = \begin{pmatrix}
    a_1 \\
    a_2 \\
    \vdots \\
    a_n
\end{pmatrix}$ và ngược lại.
- **Mục đích** của phép chuyển vị là để cho việc nhân vector với matrix được dễ dàng.

- Khi viết $x = (a_1, a_2, ... a_n)$ ta hiểu đây là vector **ngang**.

### Phép nhân vector/matrix:
- Phép nhân matrix: [Tiếng anh](https://en.wikipedia.org/wiki/Matrix_multiplication), [Tiêng việt](https://vi.wikipedia.org/wiki/Ph%C3%A9p_nh%C3%A2n_m%E1%BB%99t_s%E1%BB%91_cho_ma_tr%E1%BA%ADn).
- Phép nhân vô hướng 2 vector: 2 vector cùng chiều $a, b$, thay vì ta viết $a.b$, ta sử dụng kí hiệu **chuyển vị** và chuyển nó thành phép **nhân ma trận** $ab^T$ hoặc $a^Tb$
- Tích có hướng của vector 3 chiều: [tiếng anh](https://en.wikipedia.org/wiki/Cross_product).
    + 2 vector $u = (a, b, c)$ và $v = (x, y, z)$ có tích có hướng $u \times v = ()$

### Kí hiệu đường thẳng *đồng nhất*:
- Vì mỗi đường thẳng trên mặt phẳng đều có phương trình dạng $ax + by + c = 0$ nên mỗi đường thẳng được chọn bởi bộ 3 số $(a, b, c)$ và ta sẽ đại diện mỗi đường thẳng bằng 1 vector **dọc** $(a, b, c)^T$.
- Vector $(0, 0, 0)^T$ sẽ **không** đại diện cho đường thẳng nào cả.
- Tập hợp các đường thẳng có dạng $(ka, kb, kc)^T$ với $k$ bất kì đều đại diện cho cùng 1 đường thẳng

### Kí hiệu điểm *đồng nhất*:
- Thay vị sử dụng cặp điểm, ta sử dụng vector **dọc** $(x, y, 1)^T$ để biểu diễn điểm $(x, y)$ trên mặt phẳng.
- **Mục đích** cho việc biểu diễn như vậy để có thể dễ dàng kiểm tra điểm $p = (x, y, 1)^T$ có thuộc đường thẳng bằng $l = (a, b, c)^T$ không bằng biểu thức $(x, y, 1).(a, b, c)^T = (ax + by + c) = 0$, hay nói cách khác, $p^Tl = 0$.
- Mở rộng ra, vector dọc $(x, y, z)^T$ có thể biểu diễn điểm $\displaystyle \left( \frac{x}{z}, \frac{y}{z} \right)$ trên mặt phẳng toạ độ.

### Tìm giao của 2 đường thẳng
- Hai đường thẳng $l_1$ và $l_2$ sẽ có giao điểm $x = l_1 \times l_2$.
- Thật vậy, $l_1(l_1 \times l_2) = 0$ và $l_2(l_1 \times l_2) = 0$, do vector $l_1 \times l_2$ trong không gian cùng song song với cả $l_1$ và $l_2$. Như vậy $l_1$ và $l_2$ đều đi qua điểm $l_1 \times l_2$

### Tìm đường thẳng qua 2 điểm
- Hai điểm $p_1$ và $p_2$ có sẽ có đường thẳng $l = p_1 \times p2$ cùng đi qua chúng.
- Cũng như trên, do $p_1.(p_1 \times p_2) = 0$ và $p_2.(p_1 \times p_2) = 0$. Như vậy $p_1$ và $p_2$ đều thuộc đường thằng $p_1 \times p_2$

### Điểm và đuường thẳng ở vô cùng.
- Các điểm có dạng $(x_1, x_2, 0)^T$ là những điểm ở vô cùng, vì ta không thể tìm thấy điểm $(x_1/0, x_2/0)$ trên mặt phẳng tọa độ.
- Tập hợp các điểm ở vô cùng tạo thành đường thẳng ở vô cùng $(0, 0, 1)^T$ (thật vậy $(a, -b, 0)^T(0, 0, 1) = 0$).
- Mọi đường thẳng $l = (a, b, c)$ đều giao với đường thẳng $(0, 0, 1)^T$ tại điểm $(b, -a, 0)^T$

### A model for the projective plane
> Todo
> Do em phần này em chưa biết dịch như thế nào.

### Tính đối lập (duality)
- Ta có thể đảo vai trò của điểm và đường thẳng cho nhau:
    + Chúng đều là vector 3 chiều dọc.
    + Biểu thức kiểm tra điểm $x$ nằm trên đường thẳng $l$ là $x^Tl = 0$ có thể đổi thành $l^Tx = 0$.
    + Ngoài ra việc tìm giao điểm và đường thẳng qua 2 điểm chúng đều có thể đảo chỗ cho nhau.
- Đây gọi là nguyên tắc đôi lập (duality principle)

### Đường conic và phương trình đường conic
> Todo

--------------------------------------

## Projective transformation - Phép biến đổi xạ ảnh.
### Định nghĩa
- Một phép xạ ảnh là một song ánh $h$ từ $\mathbb{P}^2$ đến chính nó thỏa mãn với 3 điểm bất kì thẳng hàng $p_1, p_2$ và $p_3$ thì 3 điểm $h(p_1), h(p_2))$ và $h(p_3)$ cũng phải thẳng hàng.
### Định lý về phép xạ ảnh.
- Phép ánh xạ $h: \mathbb{P}^2 \to \mathbb{P}^2$ là phép xạ ảnh khi và chỉ khi tồn tại 1 matrix khả nghịch $3 \times 3$ $H$ thỏa mãn với điểm bất kì thuộc mặt phẳng đc biểu diễn bởi vector $x$ thì $h(x) = Hx$.
- Cụ thể, với điểm $x = (a, b, c)^T$ và matrix $H = \begin{bmatrix}
    h_{11} & h_{12} & h_{13} \\
    h_{21} & h_{22} & h_{23} \\
    h_{31} & h_{32} & h_{33}
\end{bmatrix}$ thì:

$$ h(x) =
\begin{bmatrix}
    h_{11} & h_{12} & h_{13} \\
    h_{21} & h_{22} & h_{23} \\
    h_{31} & h_{32} & h_{33}
\end{bmatrix}
\begin{pmatrix} a \\ b \\ c \end{pmatrix}
= \begin{pmatrix} a' \\ b' \\ c' \end{pmatrix}$$

### Ánh xạ giữa 2 mặt phẳng
![central projection](./central-projection.png)
*Hình 1: Phép xạ ảnh xuyên tâm từ 1 điểm trên mặt phẳng này đến mặt phẳng khác*

Hình 1 là một ví dụ cho cách định lý trên được áp dụng như thế nào. Với mỗi một điểm bất kì $x$ thuộc mặt phẳng $\pi$ đều có một điểm $x'$ trên mặt phẳng $\pi'$ tương ứng với điểm $x$ là giao của $\pi'$ với $Ox$ và ngược lại. Hiển nhiên ánh xạ này là một song ánh.

### Xạ ảnh của đường thẳng và đường conic
- Với phép xạ ảnh điểm $x' = Hx$ thì điểm $x'$ sẽ nằm trên đường thẳng $l' = H^{-T}l$.
    + Thật vậy, vì $l^Tx = 0$ nên
    $$l^TH^{-1}Hx = 0 \iff (H^{-T}l)^THX = 0$$, hay điểm $Hx$ sẽ nằm trên đường thẳng $H^{-T}l$.
- Như vậy với sự biến đổi điếm $x' = Hx$ thì đương thẳng $l'$ lại được biến đổi thành $H^{-T}l$.
> Todo: xạ ảnh của đường conic