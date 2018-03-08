# Mặt phẳng tại vô cùng
Trên mặt phẳng xạ ảnh, việc xác định đường thẳng $l_\infty$ giúp chúng ta đo được nhưng tính chất affine và xác định được 2 điểm tròn nằm trên $l_\infty$ giúp chúng ta đo được những tính chất metric (góc). Trong không gian xạ ảnh cũng có 2 đối tượng tương tự đó là mặt phẳng tại vô cùng $\pi _\infty$ và đường conic $\Omega _\infty$.

Mặt phẳng tại vô cùng có tọa độ $(0, 0, 0, 1)^T$ và chứa tất cả cấc điểm có dạng $(x_1, x_2, x_3, 0)^T$. Ta có:
- 2 mặt phẳng song song khi và chỉ khi đường thẳng giao của chúng nằm trên $\pi _\infty$
- Một đường thẳng song song với đường thẳng khác, hoặc với một mặt phẳng, khi giao điểm nằm trên $\pi _infty$.

Mặt phẳng tại vô cùng là yếu tố cần thiết để khôi phục tính Affine bởi vì nó không bị thay đổi sau bất kì phép affine nào. Nhưng mặt phẳng tại vô cùng lại có thể được nhìn thấy (bị di chuyển) sau phép biến đổi projective. Cũng tương tự như $l_\infty$, ta cũng có 2 nhận xét:
- Mặt phẳng tại vô cùng trong trường hợp thông thường luôn được cố định sau phép affine, nhưng các điểm trên mặt phẳng này không tương ứng 1-1.
- Ngoài $p_\infty$ ra còn một số mặt phẳng khác cũng được cố định sau phép affine.

**Khôi phục tính chất affine**. Ở những chương sau ta sẽ có những thuật toán xác định $\pi_\infty$ từ multiple view, và ta có thể xác định được những tính chất affine, như 2 mặt phẳng sẽ song song với nhau khi mặt phẳng giao nàm trên $\pi_\infty$, hoặc ta có thể sử dụng một phép biến đổi projective để đưa lại $\pi_\infty$ về vị trí ban đầu của nó $(0, 0, 0, 1)$ và đo trực tiếp trên hệ trục tọa độ mới xây dựng được.

# Đường conic tuyệt đối (The absolute conic)
Đường conic tuyệt đối $\Omega_\infty$ là conic (điểm) nằm trên mặt phẳng $\pi_\infty$. Điểm nằm trên $\Omega_\infty$ thỏa mãn hệ phương trình:
$$\begin{cases}
x_1^2 + x_2^2 + x_3^2 &= 0\\
x_4 &= 0
\end{cases}$$

Với những điểm trên $\pi_\infty$ (với $x_4 = 0$), thì ta có thể viết lại phương trình trên thành: 
$$(x_1, x_2, x_3)I(x_1, x_2, x_3)^T = 0$$

Như vậy conic $\Omega_\infty$ sẽ tương ứng với conic $C$ với matrix $C = I$. Như vậy các điểm trên $C$ hoàn toàn là các điểm ảo.

Đường conic tuyệt đối có dof 5 và tính chất quan trọng nhất của nó là $\Omega_\infty$ không bị biến đổi sau phép biến đổi similarity. Chứng minh điều này không quá khó, nên phần chứng minh sẽ không trình bày vào đây nữa. Sau đây là một vài tính chất của $\Omega_\infty$:
- $\Omega_\infty$ luôn được cố định sau mỗi phép similarity, nhưng các điểm trên nó không tương ứng 1-1.
- Tất cả các đường tròn đều cắt $\Omega_\infty$ tại 2 điểm. Có thể thấy rằng mặt phẳng $\pi$ chứa đường tròn sẽ cắt $\pi_\infty$ tại 1 đường thẳng, và đường thẳng này sẽ cắt $\Omega_\infty$ tại 2 điểm. 2 điểm này là những điểm tròn của $\pi$.
- Tất cả các hình cầu đều cắt $\pi_\infty$ tại $\Omega_\infty$.

## Tính metric
Một khi $\Omega_\infty$ đã được xác định, vậy thì các tính chất, như góc và đường thẳng có thể được đo bởi $\Omega_\infty$.
Giả sử 2 đường thẳng có 2 vector chỉ phương (vector 3 chiều) là $d_1$ và $d2$. Trong hình học Euclidean, ta có thể đo góc giữa 2 đường thẳng như sau:

$$\cos \theta = \frac{d_1^Td_2}{(d_1^Td_1)(d_2^Td_2)}$$

Ta có thể viết lại công thức thành:
$$\cos \theta = \frac{d_1^T \Omega_\infty d_2}{(d_1^T \Omega_\infty d_1)(d_2^T \Omega_\infty d_2)}$$

với $d_1$ và $d_2$ lần lượt là giao điểm của 2 đường thẳng với $\pi_\infty$ và $\Omega_\infty$ là phương trình của đường conic tuyệt đối trên $\pi_\infty$.

Công thức đầu tiên có thể suy ra từ công thức thứ hai khi thay $\Omega_\infty = I$. Tuy nhiên công thức thứ hai luôn đúng khi ta xác định được $\Omega_\infty$.

**TODO: Orthogonality and polarity**

# Mặt bậc hai đối lập tuyệt đối (The absolute dual quadric)
Đường conic tuyệt đối là 1 conic nằm trên mặt phẳng tại vô cùng. Đối lập với nó lại là một mặt bậc 2 suy biến trong không gian, gọi là mặt bậc hai đối lập tuyệt đối, kí hiệu $Q_\infty^*$. Về mặt đại số, mặt bậc hai này là một matrix $4 \times 4$ rank 3:
$$Q^*_\infty = \begin{bmatrix}
    I & \mathbf{0} \\
    \mathbf{0}^T & 0
\end{bmatrix}$$

Ta có thể chỉ ra rằng mọi mặt phẳng trong $Q^*_\infty$ đều tiếp xúc với $\Omega_\infty$, như vậy $Q^*_\infty$ sẽ hoàn toàn đối lập với $\Omega_\infty$. Xét mặt phẳng có tọa độ $\pi = (\mathbf{v}^T, k)^T$. Mặt phẳng được bao bởi $Q^*_\infty$ khi và chỉ khi $\pi^T Q^*_\infty \pi = 0$. Phương trình tương đương với $\mathbf{v}^T\mathbf{v} = 0$. Mặt khác, $\mathbf{v}$ chính là tọa độ của đường thẳng giao giữa $\pi$ và $\pi_\infty$, như vậy $\mathbf{v}$ sẽ là tiếp tuyến của $\Omega_\infty$ khi và chỉ khi $\mathbf{v}^T I \mathbf{v} = 0$. Ta có điều phải chứng minh. Có cách chứng minh khác cũng rất thú vị, tuy nhiên để đảm bảo dung lượng quyển sách nên chứng minh này sẽ không được đề cập ở đây.

$Q^*_\infty$ có dof 8, thật vậy matrix đối xứng $4 \times 4$ có dof 10, ta bỏ qua sự scale của matrix và thêm điều kiện định thức của matrix là 0. $Q^*_\infty$ có những điểm lợi so với $\Omega_\infty$ về mặt tính toán. Điều đó được thể hiện qua 3 tính chất sau:

* $Q^*_\infty$ không bị biến đổi dưới phép biến đổi similarity. 
* $\pi_\infty$ là nhân của $Q^*_\infty$. Điều này có thể suy ra được khi nhân matrix $Q^*_\infty$ với toạ độ $\pi_\infty$. Ta cũng có thể thấy rằng tính chất này luôn đúng sau khi hệ trục bị biến đổi. Thật vậy với biến đổi điểm $X' = HX$ thì $Q^{*\prime} _\infty  = HQ^*_\infty H^T$ và $\pi'_\infty = H^{-T} * \pi_\infty$. Ta có:
$$Q^{*\prime}_\infty \pi'_\infty = (HQ^*_\infty H^T)H^{-T}\pi_\infty = HQ^*_\infty \pi_\infty = 0$$
* Góc giữa 2 mặt phẳng $\pi_1$ và $\pi_2$ có thể được tính như sau:

$$\cos \theta = \frac
{\pi^T_1 Q^*_\infty \pi_2}
{
    (\pi^T_1 Q^*_\infty \pi_1)
    (\pi^T_2 Q^*_\infty \pi_2)
}
$$