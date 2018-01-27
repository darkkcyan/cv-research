# Projective transformation - Phép biến đổi xạ ảnh.
## Định nghĩa
- Một phép xạ ảnh là một song ánh $h$ từ $\mathbb{P}^2$ đến chính nó thỏa mãn với 3 điểm bất kì thẳng hàng $p_1, p_2$ và $p_3$ thì 3 điểm $h(p_1), h(p_2))$ và $h(p_3)$ cũng phải thẳng hàng.
## Định lý về phép xạ ảnh.
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
= \begin{pmatrix}
    ah_{11} + bh_{12} + ch_{13} \\
    ah_{21} + bh_{22} + ch_{23} \\
    ah_{31} + bh_{32} + ch_{33}
\end{pmatrix}
= \begin{pmatrix} a' \\ b' \\ c' \end{pmatrix}$$

## Ánh xạ giữa 2 mặt phẳng
![central projection](./transformations-central-projection.png)
*Hình 1: Phép xạ ảnh xuyên tâm từ 1 điểm trên mặt phẳng này đến mặt phẳng khác*

Hình 1 là một ví dụ cho cách định lý trên được áp dụng như thế nào. Với mỗi một điểm bất kì $x$ thuộc mặt phẳng $\pi$ đều có một điểm $x'$ trên mặt phẳng $\pi'$ tương ứng với điểm $x$ là giao của $\pi'$ với $Ox$ và ngược lại. Hiển nhiên ánh xạ này là một song ánh.

## Xạ ảnh của đường thẳng và đường conic
- Với phép xạ ảnh điểm $x' = Hx$ thì điểm $x'$ sẽ nằm trên đường thẳng $l' = H^{-T}l$.
    + Thật vậy, vì $l^Tx = 0$ nên
    $$l^TH^{-1}Hx = 0 \iff (H^{-T}l)^THX = 0$$, hay điểm $Hx$ sẽ nằm trên đường thẳng $H^{-T}l$.
- Như vậy với sự biến đổi điếm $x' = Hx$ thì đương thẳng $l'$ lại được biến đổi thành $H^{-T}l$.
> Todo: xạ ảnh của đường conic

# A hierarchy of transformations
Tạm dịch là "cấp của các phép biến đổi"

## Lớp I: Isometries
"Iso" là giống nhau (same), "metric" là độ dài (mesure). Đây là phép biến đổi đảm bảo được khoảng cách Euclidean trên mặt phẳng. Phép biến đổi có thể là phép tịnh tiến, xoay, lấy đối xứng hoặc là phép biến đổi kết hợp giữa các phép đó.
### Biểu diễn của phép biến đổi Isometries
$$
\begin{pmatrix} x' \\ y' \\ z' \end{pmatrix}
= \begin{bmatrix}
    \epsilon cos\theta & -sin\theta & t_x \\
    \epsilon sin\theta & cos\theta & t_y \\
    0 & 0 & 1
\end{bmatrix}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
$$
Trong đó:
    - $(t_x, t_y)$ là vector tịnh tiến.
    - $\theta$ là góc quay.
    - $\epsilon \in {-1, 1}$. nếu $\epsilon = 1$ thì đây là phép biến đổi cùng chiều, ngược lại đây là phép biến đổi ngược chiều (tức là đối xứng gương).
Hay ta có thể  viết dưới block form:
$$ x' = H_Ex = \begin{bmatrix}
R & t \\ 0^T & 1
\end{bmatrix}x$$
Với $R$ là matrix $2 \times 2$ trực giao (tức $R^TR = RR^T = I$ là ma trận cơ sở), $t$ là vector tịnh tiên. Nếu $R = I$, đây là phép thuần tịnh tiến, còn $t$ là vector 0 thì đây là phép thuần xoay.
### Những thành phần bất biến (invariants)
Bao gồm độ dài, góc, và diện tích sẽ bất biến sau khi biến đổi.

## Lớp II: Similarity transformations
Đôi khi gọi là similarity, là phép Isometry kết hợp với phép scale (co dãn).
### Biểu diễn của phép biến đổi Similarity.
Gần giống với Isometries.
$$
\begin{pmatrix} x' \\ y' \\ z' \end{pmatrix}
= \begin{bmatrix}
    \pm s.cos\theta & -s.sin\theta & t_x \\
    \pm s.sin\theta & s.cos\theta & t_y \\
    0 & 0 & 1
\end{bmatrix}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
$$
Hay block form:
$$ x' = H_Sx = \begin{bmatrix}
sR & t \\ 0^T & 1
\end{bmatrix}x$$
Trong đó $s$ là hệ số scale.

### Thành phần bất biến.
Góc vẫn được dữ nguyên nhưng khoảng cách thì không. Thay vào đó thì tỉ lệ giữa 2 đoạn thẳng song song nhau vẫn được bảo toàn. Ngoài ra tỉ lệ diện tichs cũng không đổi.

## Lớp III: Affine transformations
Đây là phép biển đổi kết hợp giữa phép biến đổi phi tuyến tính với phép biến đỏi tịnh tiến.

### Biểu diễn của phép Affine transformation.
$$
\begin{pmatrix} x' \\ y' \\ z' \end{pmatrix}
= \begin{bmatrix}
    a_{11} & a_{12} & t_x \\
    a_{21} & a_{22} & t_y \\
    0 & 0 & 1
\end{bmatrix}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
$$
Hay block form:
$$ x' = H_Sx = \begin{bmatrix}
A & t \\ 0^T & 1
\end{bmatrix}x$$

![Affine-transformation](transformations-affine-transformation.png)
*Hình 2: ví dụ về phép biến đổi affine*.

Để dễ hiểu hơn ta có thể viết ma trận $A$ dưới dạng:
$$A = R(\theta)R(-\phi)DR(\phi)$$
Trong đó $R(x)$ là ma trận $2\times2$ thể hiện phép xoay một góc $x$ (như ma trận $R$ ở lớp $I$), và $D$ là ma trận $2\times2$ có dạng $\begin{bmatrix}
    \lambda_1 & 0 \\
    0 & \lambda_2
\end{bmatrix}$ thể hiện phép scale theo hệ số $\lambda_1$ và $\lambda_2$ tương ứng với trục hoành và tung. Tóm lại, $A$ sẽ thực hiện: quay một góc $\phi$, scale theo ma trận $D$, xoay hình ngược lại góc $\phi$ và cuối cùng lại xoay một góc $\theta$. Vd như hình 2b, đầu tiên ta xoay hình vuông theo góc $\phi$, dãn hình theo trục tung và co hình theo trục hoành rồi xoay hình lại góc $-\phi$.

### Các thành phần bất biến
Các đường thẳng song song vẫn song song.
> Thật vậy các đường thẳng song song ban đầu cắt nhau tại một điểm ở vô cùng $(x_1, y_1, 0)^T$ nào đó, sau phép biến đổi, điểm này sẽ có ảnh vẫn là một điểm tại vô cũng, như vậy 2 đường thẳng vẫn tiếp tục cắt nhau tại vô cùng.

Tỉ lệ độ dài giữa các đoạn thẳng song song được bảo tồn.
> Thật vậy, độ dài của các đoạn thẳng chỉ phụ thuộc vào độ lệch góc giữa phương của đoạn thẳng và phương scale. Giả sử ta đang có phép scale theo trục (orthogonal) và đoạn thẳng lệch so với trục hoành góc $\alpha$, vậy tỉ lệ giữa độ lớn đoạn thẳng mới và cũ là $\sqrt{\lambda_1^2 cos^2\alpha + \lambda_2^2sin^2\alpha}$ và tỉ lệ này áp dụng cho mọi đường thẳng lệch góc $\alpha$.

Tỉ lệ diện tích được bảo tồn.
> Thật vậy diện tích chỉ phụ thuộc vào sự scale. Và tỉ lệ diệc tích mới so với diện tichs cũ luôn là $\lambda_1\lambda_2$.

## Lớp IV: Projective transformations
Cũng giống như Affine transformations, nhưng vì ta đang sử dụng quy ước điểm và đường thẳng đồng nhất, như vậy ta có thể thay hàng cuối của ma trận biến đổi thành 1 ma trận khác.
### Biểu diễn của Projective transformation
Biểu diễn ở block form:
$$ x' = H_Sx = \begin{bmatrix}
A & t \\ \mathrm{v}^T & v
\end{bmatrix}x$$

Trong đó $\mathrm{v}^T = (v_1, v_2)$
### Thành phần bất biến
- Crossratio của 4 điểm thẳng hàng bằng nhau (sẽ nói rõ hơn ở phần sau).

### So sánh với Affine transformations
Nhận xét với một điểm $(x_1, x_2, 0)^T$ ở vô cùng, thì với Affine transformations:
$$
\begin{bmatrix}A & t \\ 0^T & 1\end{bmatrix}
\begin{pmatrix}x_1 \\ x_2 \\ 0\end{pmatrix}
= \begin{pmatrix}
    A\begin{pmatrix}x_1 \\ x_2\end{pmatrix} \\
    0
\end{pmatrix}
$$
sẽ cho ra một điểm tại vô cùng, còn với projective transformation:
$$
\begin{bmatrix}A & t \\ \mathbf{v}^T & v\end{bmatrix}
\begin{pmatrix}x_1 \\ x_2 \\ 0\end{pmatrix}
= \begin{pmatrix}
    A\begin{pmatrix}x_1 \\ x_2\end{pmatrix} \\
    v_1x_1 + v_2x_2
\end{pmatrix}
$$
lại cho ra một điểm ko tại vô cùng. Điều này cho phép projective transformation **dựng lên những điểm không thực sự tồn tại**.

---