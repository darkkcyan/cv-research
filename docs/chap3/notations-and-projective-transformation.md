# Quy ước và phép biến đổi xạ ảnh

> Note: Khi nói đến sự scale của matrix, ta hiểu 2 matrix $A$ và $\alpha A$ với $\forall \alpha \ne 0$ đều chỉ một matrix nếu như matrix này đồng nhất.

> Note: projective có nghĩa là xạ ảnh trong tiếng Việt.

## Điểm
Trên $\mathbb{P}^2$, tọa độ điểm là 1 vector 3 chiều thì trong $\mathbb{P} ^ 3$ vector này sẽ có 4 chiều. Cụ thể, vector $(x_1, x_2, x_3, x_4)^T$ trên hệ tọa độ đồng nhất sẽ biểu diễn điểm có tọa độ $(x_1/x_4, x_2/x_4, x_3/x_4)^T$ trên hệ tọa độ không đồng nhất khi $x_4 \ne 0$.

Khi $x_4 = 0$ thì điểm $(x_1, x_2, x_3, x_4)$ sẽ biểu diễn điểm tại vô cùng.

Và như vậy điểm có dof 3.

## Phép biến đổi xạ ảnh (Projective transformation).
Phép biến đổi xạ ảnh trên $\mathbb{P}^3$ là phép biến đổi tuyến tính vector đồng nhất 4 chiều, được biển diễn bởi 1 matrix khả nghịch $4 \times 4$. Với điểm $X = (x_1, x_2, x_3, x_4)^T$ và phép biến đổi xạ ảnh với ma trận $H$ thì điểm sau khi biến đổi sẽ là $X' = HX$.

Matrix của phép biến đổi xạ ảnh là matrix đồng nhất có dof 15 vì có 16 ô và giảm đi 1 khi ta không tính scale matrix, nói cách khác, 2 matrix $H$ và $kH$ ($k \ne 0$) biểu diễn cùng 1 phép biến đổi.

## Mặt phẳng
Khác với $\mathbb{P}^2$, trong $\mathbb{P}^3$, điểm sẽ đối lập với mặt phẳng chứ không phải đường thẳng.

Ta biết rằng trên hệ tọa độ không đồng nhất, mặt phẳng có phương trình:

$$\pi_1 X + \pi_2 Y + \pi_3 Z + \pi_4 = 0$$

Ta có thể đồng nhất hóa phương trình này bằng cách thay
$X = x_1 / x_4, Y = x_2/_x4, Z = x_3 / x_4$, ta thu được phương trình mặt phẳng trên hệ tọa độ đồng nhất.

$$\pi_1 x_1 + \pi_2 x_2 + \pi_3 x_3 + \pi_4 x_4 = 0$$

Hay ta có thể viết thành dạng tích vector $\pi^T X = 0$ với $X$ là điểm nằm trên mặt phẳng $\pi$

Ta có thể thấy rằng với hệ tọa độ không đồng nhất, khi phương trình trên được viết lại thành
$n\tilde{X} + d = 0$ với $n = (\pi_1, \pi_2, \pi_3)^T; \tilde{X} = (x_1, x_2, x_3)^T; d = \pi_3; x_4 = 1$, thì khoảng cách từ $\pi$ đến gốc tọa độ là $d / \|n\|$.

### Các mối quan hệ giao và hợp
Trên $\mathbb{P}^3$ có rất nhiều mỗi quan hệ, điển hình:
- 3 điểm, hoặc 1 điểm và một đường thẳng có thể xác định duy nhất một mặt phẳng ở vị _thông thường*_ (hay nói cách khác, trường hợp mà 3 điểm không thẳng hàng hoặc điểm không nằm trên đường thẳng).
- 2 mặt phẳng bất kì giao nhau tại duy nhất 1 đường thẳng.
- 3 mặt phẳng bất kì giao nhau tại duy nhất 1 điểm.

### Ba điểm xác định một đường thẳng
Giả sử ta có 3 điểm $X_1, X_2, X_3$ nằm trên mặt phẳng $\pi$, như vậy ta có 3 phương trình $\pi^T X_i = 0$. Chồng 3 điểm này lên ta có ma trận $3\times 4$ và phương trình của ta trở thành:
$$
\begin{bmatrix}
    X_1^T \\
    X_2^T \\
    X_3^T
\end{bmatrix} = \mathbf{0}
$$

Tại vị trí thông thường, 3 điểm này sẽ độc lập tuyến tính với nhau, nên ta thu được matrix $3\times4$ có rank 3, và như vậy mặt phẳng được xác định duy nhất (bỏ qua yếu tố scale ma trận). Nếu như matrix thu được có rank 2, thì 3 điểm là 3 điểm thẳng hàng, như vậy nghiệm của phương trình sẽ là họ các mặt phẳng đi qua đường thẳng chứa 3 điểm.

Trong $\mathbb{P}^2$, đường thẳng cũng có thể xác định bằng cách trên (từ 2 điểm tạo một ma trận $2 \times 3$ và lập phương trình), và ngoài ra còn có công thức rất nhanh gọn nhờ tích có hướng $l = X \times Y$. Trong $\mathbb{P}^3$ ta cũng có thể xây dựng nên công thức tương tự nhờ định thức và các phép biến đổi sơ cấp.

Bắt đầu với ma trận $4 \times 4$, $M = [X, X_1, X_2, X_3]$ với $X$ là một điểm bất kì và $X_1, X_2, X_3$ là 3 điểm xác định mặt phẳng $\pi$. Điểm $X$ sẽ nằm trên $\pi$ khi $\det M = 0$ vì khi đó $X$ là một tổ hợp tuyến tính của 3 điểm $X_i$. Viết lại:

$$ \det M = x_1 D_{234} - x_2 D_{134} + x_3 D_{124} - x_4 D_{123}$$

Với $D_{ijk}$ là định thước của ma trận tạo bởi 3 hàng $ijk$ của ma trận $3 \times 4$ $[X_1, X_2, X_3]$. Và vì $\det M = 0$ khi $X \in \pi$ nên phương trình $\pi$ cũng có dạng:

$$\pi = (D_{234}, -D_{134}, D_{124}, -D_{123})^T$$

#### Trường hợp đặc biệt
Nếu giả sử 3 điểm $X_i$ có dạng:

$$
X_1 = \begin{pmatrix} \tilde{X}_1 \\ 1 \end{pmatrix},
X_2 = \begin{pmatrix} \tilde{X}_2 \\ 1 \end{pmatrix},
X_3 = \begin{pmatrix} \tilde{X}_3 \\ 1 \end{pmatrix}
$$

Với $\tilde{X} = (X, Y, Z)$. Vậy thì

$$
D_{234} = \begin{vmatrix}
    Y_1 & Y_2 & Y_3 \\
    Z_1 & Z_2 & Z_3 \\
    1   & 1   & 1
\end{vmatrix}
= \begin{vmatrix}
    Y_1 - Y_3 & Y_2 - Y_3 & Y_3 \\
    Z_1 - Z_3 & Z_2 - Z_3 & Z_3 \\
    0         & 0         & 1
\end{vmatrix}
=\left(
    (\tilde X _1 - \tilde X _ 3) \times
    (\tilde X _2 - \tilde X _ 3)
\right)_1
$$
Nói cách khác, ta thu được $D_{234}$ là ô đầu tiên của $(\tilde X _1 - \tilde X _ 3) \times (\tilde X _2 - \tilde X _ 3)$. Tương tự như vậy, cuối cùng ta có $(D_{234}, -D_{134}, D_{124}) =(\tilde X _1 - \tilde X _ 3) \times (\tilde X _2 - \tilde X _ 3) $ và phương trình mặt phẳng sẽ là:

$$\pi = \begin{pmatrix}
    (\tilde X _1 - \tilde X _ 3) \times (\tilde X _2 - \tilde X _ 3) \\
    - \tilde X _3 (\tilde X _1 \times \tilde X _2)
\end{pmatrix}
$$

Công thức này rất giống với hình học Euclide, khi mà ta tính vector pháp tuyến của mặt phẳng cũng chính bởi công thức: $(\tilde X _1 - \tilde X _ 3) \times (\tilde X _2 - \tilde X _ 3)$. Tuy nhiên vẫn phải lưu ý đâu là trường hợp đặc biệt, ta phải đảm bảo rằng không có điểm nào trong 3 điểm là điểm tại vô cùng.

### Ba mặt phẳng xác định một điểm.
Vì điểm và mặt phẳng đối lập nhau, ta có thể tìm điểm cũng thương tự như trên, chồng 3 tọa độ mặt phẳng lên để được ma trận $3 \times 4$ và giải phương trình tương tự để tìm điểm.

### Phép biến đổi xạ ảnh với mặt phẳng
Khi điểm được biến đổi bởi phép biến đổi $X' = HX$ thì mặt phẳng $\pi$ được biến đổi theo công thức $\pi = H^{-T}\pi$, tương tự như trên $\mathbb{P}^2$.

### Tham số hóa cho điểm thuộc mặt phẳng
Điểm $X$ thuộc mặt phẳng $\pi$ có thể viết thành:

$$X = Mx$$

Với $M$ là matrix $4 \times 3$ rank 3 gồm các cột là các điểm nằm trên $\pi$, hay $\pi^TM = 0$ và $x$ là một điểm bất kì trên $\mathbb{P}^2$. Nói cách khác, 3 cột của $M$ tạo thành tập cơ sở của không gian vector con của $\mathbb{P}^3$ mà tất cả các vector trong không gian này đều nằm trên mặt phẳng $\pi$. Và vì một không gian vector có thể có nhiều tập cơ sở, nên $M$ không phải duy nhất.

Với $\pi = (a, b, c, d)$ và $a \ne 0$ thì ta có một matrix $M$ có dạng $[(-b/a, -c/a, -d/a)^T \mid \mathbf {I}]^T$.

## Đường thẳng
Một đường thẳng được xác định khi nối 2 điểm, hoặc lấy giao của 2 mặt phẳng. Để đơn giản hơn, đầu tiên ta có thể lấy 2 mặt phẳng cố định vuông góc với nhau. 2 điểm bất kì mà mỗi điểm nằm trên một mặt phẳng sẽ xác định một đường thẳng. Vi mặt phẳng đã cố định, và mỗi điểm trên mặt phẳng ($\mathbb{P}^2$) có dof 2, nên đường thẳng sẽ có dof 4.

![line-presentation](./notations-and-projective-transformation-line-presentation.png)
*Biểu diễn đường thẳng đi qua 2 điểm thuộc 2 mặt phẳng cố định vuông góc.*

Vì dof của đường thẳng là 4 nên có vẻ như tọa độ đường thẳng sẽ được biểu diễn bởi vector 5 chiều. Nhưng như vậy sẽ rất khó để tương tác với điểm và mặt phẳng khi chúng chỉ là vector 4 chiều. Đã có rất nhiều cách biểu diễn đường thẳng đã được đề xuất để giảm thiểu sự lúng túng này. Dưới đây là 3 trong số các cách biểu diễn.

### Nhân và biểu diễn theo không gian vector
> Ngoài từ kernal còn từ nullspace đều có nghĩa là nhân trong đại số tuyến tính.

Biểu diễn dựa trên nhận xét: 2 điểm (hoặc mặt phẳng) đều xác định duy nhất 1 đường thẳng. Cách biểu diễn khá đơn giản, nhưng ta có thể thấy rằng các lấy điểm và mặt phẳng nhiều lúc lại không quá quan trọng (vì tổng dof của 2 điểm (2 mặt phẳng) là 6, trong khi đường thẳng chỉ có 4).

#### Biểu diễn đường thẳng theo 2 điểm
Giả sử ta có 2 điểm không thẳng hàng $A, B$, như vậy đường thẳng đi qua hai điểm này có thể được biểu diễn thành:
$$W = \begin{bmatrix}
    A ^ T \\ B ^ T
\end{bmatrix}$$

Như vậy:
- Không gian cột của $W^T$ là họ các điểm có dạng $\lambda A + \mu B$, nằm trên cùng một đường thẳng.
- Nhân của $W$ là không gian vector có dim 2 và là họ các mặt phẳng đi qua đường thẳng.

#### Biểu diễn đường thẳng theo 2 mặt phẳng
Biểu diễn đối lập với biểu diễn trên là ta sử dụng mặt phẳng thay vì điểm:

$$W^* = \begin{bmatrix} P^T \\ Q^T \end{bmatrix}$$

Và các tính chất cũng tương tự:
- Không gian cột của $W^{*T}$ là họ các mặt phẳng chứa đường thẳng.
- Nhân của $W$ là họ các điểm thuộc đường thẳng.

Ngoài ra ta có thể nhận thấy $WW^{*T} = W^TW^* = 0$.

#### Tìm điểm và mặt phẳng có quan hệ với đường thẳng
Ta có thể tìm mặt phẳng từ điểm $X$ và đường thẳng $W$ nhờ tìm nhân của matrix:

$$M = \begin{bmatrix}
    W \\ P^T
\end{bmatrix}$$

Nếu $null(M) = 2$ thì $P \in W$, ngược lại ta có thể tìm được duy nhât 1 mặt phẳng.

Với điểm là giao của mặt phẳng $\pi$ và đường thẳng $W$ ta có thể tìm nhân của matrix:

$$M = \begin{bmatrix}
    W^* \\ \pi^T
\end{bmatrix}$$

Nếu $null(M) = 2$ thì $W \subset \pi$, ngược lại xác định duy nhất 1 điểm.

### Plücker matrix
Đây là cách biểu diễn đường thẳng bởi một matrix đồng nhất đối xứng lệch $4 \times 4$. Đường thẳng đi qua 2 điểm $A$ và $B$ sẽ có các ô của matrix tính toán bởi công thức:
$$l_{ij} = A_iB_j - B_iA_j$$
Hay:
$$L = AB^T - BA^T$$

Một vài tính chất đầu tiên của cách biểu diễn này:
- $rank(L) = 2$, nhân dim 2 của $L$ là họ các mặt phẳng đi qua đường thẳng (thực tế, $LW^{*T} = 0$).
- $\det L = 0$, điều náy sẽ được giải thích ở phần dưới.
- Dof của $L$ là 4. Ta có thể tính toán như sau: matrix đối xứng lệch có 6 phần tử khác không độc lập với nhau, và ta giảm đi 1 vì ta đang xét matrix đồng nhất, cuối cùng do $\det L = 0$, nên dof của $L$ là 4.
- Quan hệ $L = AB^T - BA^T$ với vector 4 chiều đã tổng quát hóa quan hệ $L = x \times y$ với vector 3 chiều.
- Matrix $L$ là duy nhất với bất kể cách chọn 2 điểm nào trên đường thẳng. Thật vậy nếu ta chọn điểm $C = A + \lambda B$, ta có:
$$\begin{aligned}
\hat{L} &= AC^T - CA^T = A(A^T + \lambda B^T) - (A + \lambda B)A^T \\
    &= AA^T + \lambda AB^T - AA^T - \lambda BA^T \\
    &= \lambda (AB^T - BA^T) \\
    &\equiv AB^T - BA^T = L
\end{aligned}$$

- Với phép biến đổi điểm $X' = HX$ thì đường thẳng sẽ được biến đổi thành $L' = HLH^T$.

Biểu diễn đối lập chính là sử dụng mặt phẳng thay cho điểm:

$$ L^* = PQ^T - QP^T $$

và nó có tính chất tương tự như $L$. Với phép biến đổi điểm $X' = HX$ thì $L^*T$ sẽ được biến đổi thành $L^{*\prime} = H^{-T}L^*H^{-1}$. Matrix $L^*$ có thể tính toán trực tiếp từ $L$ một cách đơn giản quy tắc viết lại như sau:
$$ l_{12} : l_{13} : l_{14} : l_{23} : l_{42} : l_{34} = 
   l_{34}^* : l_{42}^* : l_{23}^* : l_{14}^* : l_{13}^* : l_{12}^*$$

Cách viết lại này rất dễ nhớ, vì chỉ số của 2 ô tương ứng với nhau sẽ nằm trong tập hợp ${1,2,3,4}$, ví dụ như ô $l_{12}$ sẽ được viết vào ô $l_{34}^*$.

#### Tìm điểm và mặt phẳng quan hệ với đường thẳng
Với cách biểu diễn này thì việc tìm lại rất đơn giản.
Tìm mặt phẳng $\pi$ là giao của điểm $X$ và mặt phẳng $L$:

$$ \pi = L^* X $$

Và nếu $L^* X = 0$, thì $X \in L$.

Còn với cách tìm điểm $X$ là giao của $L$ và mặt phẳng $\pi$:

$$X = L\pi$$

Và tương tự, $L\pi = 0$, thì $L \subset \pi$.

#### Hệ tọa độ đường thẳng Plücker.
Mỗi đường thẳng trong $\mathbb{P}^3$ khi được biểu diễn bởi matrix Plücker có thể được biểu diễn trên hệ tọa độ Plücker là 1 vector 6 chiều là 6 phần tử khác 0 độc lập với nhau trong matrix $L$, cụ thể:

$$\mathcal{L} = \{l_{12}, l_{13}, l_{14}, l_{23}, l_{42}, l_{34}\}$$

Vì đây là vector 6 chiều đồng nhất nên đây là một phần tử của $\mathbb{P}^5$. Từ $\det L = 0$, ta có:

$$l_{12} l_{34} + l_{13} l_{42} + l_{14} l_{23} = 0$$

Và mỗi vector 6 chiều chỉ thỏa mãn là một đường thẳng trong $\mathbb{P}^3$ khi thỏa mãn phương trình trên. Phương trình trên chính là phương trình của mặt bậc 2 trong $\mathbb{P}^5$, được biết đến với tên *Klein quadric*.

Giả sử 2 đường thẳng $\mathcal L$ và $\hat\mathcal L$ lần lượt nối 2 cặp điểm $A, B$ và $\hat A, \hat B$. Hai đường thẳng sẽ cắt nhau khi 4 điểm đó đồng phẳng. Một trong những điều kiện để 4 điểm đó đồng phẳng là $\det [A, B, \hat A, \hat B] = 0$. Ta có thể triển khai nó thành:
$$
\begin{aligned}
\det [A, B, \hat A, \hat B] &= 
l_{12}\hat l _{34} + \hat l _{12}l_{34} +
l_{13}\hat l _{24} + \hat l _{13}l_{24} +
l_{14}\hat l _{23} + \hat l _{14}l_{23} \\
&= (\mathcal L \mid \hat\mathcal L)
\end{aligned}
$$

Vì trên hệ tọa độ Plücker, các đường thẳng luôn độc lập với việc chọn điểm, nên tích _song tuyến tính*_ $(\mathcal L \mid \hat \mathcal L)$ cũng độc lập với việc chọn điểm và chỉ phụ thuộc vào việc chọn $\mathcal L$ và $\hat \mathcal L$. Như vậy ta có định lý:
> Hai đường thẳng $\mathcal L$ và $\hat \mathcal L$ cắt nhau khi $(\mathcal L \mid \hat\mathcal L)= 0$

> _song tuyến tính*_: Tra google rất nhiều lần nhưng người dịch vẫn không biết từ bilinear producted nghĩa là gì nên tạm dịch như vậy, và kí hiệu $(\mathcal L \mid \hat\mathcal L)$ từ đâu ra, có thể đây là kí hiệu chỉ có trong sách.

Từ tích này ta có thể rút ra được một số công thức hữu ích khác:
- Một vector 6 chiều $\mathcal L$ chỉ biểu diễn một đường thẳng trong $\mathbb P ^3$ khi $(\mathcal L \mid \mathcal L) = 0$. Công thức này tương tự công thức ở phía trên.
- 2 đường thẳng $\mathcal L$ và $\hat \mathcal L$ lần lượt là giao của 2 cặp mặt phẳng $P, Q$ và $\hat P, \hat Q$ thì tương tự, $(\mathcal L \mid \hat\mathcal L) = \det [P, Q, \hat P, \hat Q]$.
- Nếu $\mathcal L$ là giao của 2 mặt phẳng $P, Q$ và $\hat\mathcal L$ nối 2 điểm $X, Y$, thì:
$$(\mathcal L \mid \hat\mathcal L) = (P^T A)(Q^T B) - (Q^T A)(P^T B)$$.

## Mặt bậc 2 (quadrics)
Mặt bậc 2 trong $\mathbb{P}^3$ được định nghĩa bởi phương trình:
$$X^T Q X = 0$$

Trong đó $Q$ là matrix đối xứng $4 \times 4$. Một vài tính chất của mặt bậc 2:
- Dof của mặt bậc 2 là 9, vì nó đối xứng nên có 10 phần tử độc lập và bỏ qua yếu tố scale.
- 9 điểm ở vị trí thông thường định nghĩa 1 mặt bậc 2.
- Nếu $Q$ không khả nghịch thì mặt bậc 2 sẽ bị suy biến và sẽ được định nghĩa bởi ít điểm hơn.
> TODO: tính chất polarity
- Giao của mặt phẳng và mặt bậc 2 là 1 conic.
- Dưới phép biến đổi điểm $X' = HX$ thì mặt bậc 2 được biến đổi thành $Q' = H^{-T}QH^{-1}$.

Đối lập với mặt bậc 2 cũng là mặt bậc 2 được xác định bởi các mặt phẳng tiếp tuyến với mặt bậc 2. Mặt phẳng $\pi$ sẽ là tiếp tuyến với mặt bậc 2 $Q$ khi $\pi^TQ^* \pi = 0$, với $Q^*$ là ma trận phó của $Q$, hay là $Q^{-1}$ nếu nó khả nghịch.
Dưới phép biến đổi điểm $X' = HX$ thì mặt bậc 2 đối lập được biến đổi thành $Q^{*\prime} = HQ^*H^{-T}$.

### Phân loại mặt bậc hai
Vì $Q$ là matrix đối xứng nên ta có thể phân giã $Q$ thành $Q = U^TDU$ với $U$ là matrix trực giao và $D$ là matrix chéo. Hơn nữa để thích hợp cho việc scale hàng matrix $U$, ta có thể viết lại thành $Q = H^TDH$ với $D$ là matrix chéo chỉ gồm các phần tử 0, 1 hoặc -1. Và cuối cùng, với biểu thức $Q = H^TDH$, khi ta coi $D$ là kết quả của phép biến đổi xạ ảnh từ $Q$. Như vậy $Q$ và $D$ tương đương nhau sau phép biến đổi xạ ảnh và $D$ được coi như dạng đơn giản của $Q$.

Ta định nghĩa _signature_ (tạm dịch là _khóa_) của $D$, kí hiệu $\sigma(D)$ là tổng số số $1$ trong $D$ trừ đi tổng số số $-1$ trong $D$. Ta có thể mở rộng định nghĩa này với $Q$ bất kì, ta có $\sigma(Q) = \sigma(D)$ với $Q = H^TDH$. Việc chọn $H$ không ảnh hưởng đến định nghĩa trên đã được người ta chứng minh. Việc định nghĩa khóa cho matrix chỉ phụ thuộc vào dấu, nên ta có thể giả sử khóa là một số không âm. Và như vậy mỗi mặt bậc hai xạ ảnh luôn được định nghĩa duy nhất dựa vào bậc và khóa của nó.

Mỗi mặt bậc hai biểu diễn bởi matrix $diag(d_1, d_2, d_3, d_4)$ biểu diễn tập hợp các điểm thỏa mãn phương trình $d_1X^2 + d_2 Y^2 + d_3 z^2 + d_4 T^2 = 0$. Nếu ta cho $T = 1$ ta sẽ có phương trình điểm không tại vô cùng của mặt bậc hai. Sau đây là bảng phân loạn các mặt bậc hai.

| Rank | $\sigma$ | Diagonal      | Phương trình      | Nhận xét                                       |
|------|----------|---------------|-------------------|------------------------------------------------|
| 4    | 4        | $(1,1,1,1)$   | $X^2+Y^2+Z^2+1=0$ | không có điểm thực                             |
| ^    | 2        | $(1,1,1,-1)$  | $X^2+Y^2+Z^2=1$   | Hình cầu                                       |
| ^    | 0        | $(1,1,-1,-1)$ | $X^2+Y^2=Z^2+1$   | Một tấm Hyperboloid (Hyperboloid of one sheet) |
| 3    | 3        | $(1,1,1,0)$   | $X^2+Y^2+Z^2 = 0$ | Duy nhất điểm $(0,0,0,1)^T$                    |
| ^    | 1        | $(1,1,-1,0)$  | $X^2+Y^2=Z^2$     | Mặt nón tại gốc tọa độ                         |
| 2    | 2        | $(1,1,0,0)$   | $X^2+Y^2=0$       | Trục z                                         |
| ^    | 0        | $(1,-1,0,0)$  | $X^2=Y^2$         | Hai mặt phẳng $X = \pm Y$                      |
| 1    | 1        | $(1,0,0,0)$   | $X^2=0$           | Mặt phẳng $X = 0$                              |

Ngoài ra mặt bậc hai còn được phân thành 2 lớp, ruled (chứa đường thẳng trong mặt) và non-ruled (không chứa đường thẳng trong mặt). 

![nonruled-quadrics](notations-and-projective-transformation-nonruled-quadrics.png)
_Các mặt bậc hai không chứa đường thẳng (non ruled)_

![ruled-quadrics](notations-and-projective-transformation-ruled-quadrics.png)
_Các mặt bậc hai chứa đường thẳng (ruled)_

## TODO: Twisted cubic