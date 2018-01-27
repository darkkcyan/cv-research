# Một số quy ước và công thức thường dùng

Để có thể biểu diễn và tính toán một cách dễ dàng các yếu tố như điểm và đường thẳng, ta sẽ không dùng hình học phẳng đã được học trong chương trình trung học mà sử dụng hình học xạ ảnh (projective geometry). Phần này gồm các kí hiệu, quy ước và công thức thường dùng làm cơ sở cho các phần sau.

## Công thức liên quan đến ma trận và vector.
Các công thức với ma trận: gồm các công thức [nhân, chuyển vị](https://vi.wikipedia.org/wiki/Ma_tr%E1%BA%ADn_(to%C3%A1n_h%E1%BB%8Dc)#C%C3%A1c_ph%C3%A9p_to%C3%A1n_c%C6%A1_b%E1%BA%A3n) và [lấy định thức](https://vi.wikipedia.org/wiki/Ma_tr%E1%BA%ADn_(to%C3%A1n_h%E1%BB%8Dc)#%C4%90%E1%BB%8Bnh_th%E1%BB%A9c).
Ngoài ra còn rank của ma trận ([wikipedia **tiếng anh**](https://en.wikipedia.org/wiki/Rank_(linear_algebra))).

Ngoài ma trận, ta còn áp dụng công thức chuyển vị với vector để **dễ dàng thực hiện phép toán với ma trận**. Với một vector ngang (hoặc dọc) $x$ thì vector dọc (hoặc ngang) tương ứng với nó là $x^T$. Cụ thể, một vector ngang $x = (a_1, a_2, ... a_n)$ sẽ có vector dọc tương ứng là $x^T = \begin{pmatrix}
    a_1 \\
    a_2 \\
    \vdots \\
    a_n
\end{pmatrix}$ và ngược lại. Kể từ đây, khi viết $x$ hay $(a_1, a_2, ... a_n)$ ta hiểu đây là vector **ngang**, còn $x^T$ hay $(a_1, a_2, ..., a_n)^T$ là vector **dọc**.

Phép nhân vô hướng 2 vector: 2 vector cùng chiều $a, b$, thay vì ta viết $a.b$, ta sử dụng phép **chuyển vị** và chuyển nó thành phép **nhân ma trận** $ab^T$ hoặc $a^Tb$.

Tích có hướng của vector 3 chiều: [wikipedia tiếng anh](https://en.wikipedia.org/wiki/Cross_product).
- 2 vector $u = (a, b, c)$ và $v = (x, y, z)$ có tích có hướng
    $$u \times v = \left(bz - cy, az - cx, ay - bx\right)$$

## Quy ước cho điểm và đường thẳng *đồng nhất*:
Như ví dụ ở phần mở đầu, hình bên trái tồn tại điểm có vẻ như *"không tồn tại"* ở hình một (điểm ở vô cùng). Vậy nhưng thật ra là vẫn tồn tại điểm như vậy, tuy nhiên điểm đó không được biểu diễn bởi cặp số $(x, y)$ thông thường và ta sử dụng hệ tọa độ "đồng nhất" để biểu diễn điểm đó bởi số.
- Ta sử dụng vector $(x, y, z)^T$ để biểu diễn điểm trên mặt phẳng. Với điểm có $z \ne 0$, thì điểm đó sẽ biểu diễn điểm $(x / z, y / z)$ trên mặt phẳng tọa độ.
Còn với $z = 0$, nhưng điểm có dạng $(x, y, 0)$ sẽ biểu diễn các điểm tại vô cùng.

Vì mỗi đường thẳng trên mặt phẳng đều có phương trình dạng $ax + by + c = 0$ nên mỗi đường thẳng được xác định bởi bộ 3 số $(a, b, c)$ và ta sẽ cũng đại diện mỗi đường thẳng bằng 1 vector $(a, b, c)^T$.
- Vector $(0, 0, 0)^T$ sẽ đại diện cho đường thẳng ở vô cùng.
- Tập hợp các đường thẳng có dạng $(ka, kb, kc)^T$ với $k$ bất kì đều đại diện cho cùng 1 đường thẳng.

Như vậy, ta có thể nhận thấy rằng một điểm $p = (x, y, z)$ sẽ nằm trên đường thẳng $l = (a, b, c)$ nào đó khi
$$p^Tl = (ax + by + cz) = 0$$

## Degrees of freedom (tạm dịch độ tự do)
Với một điểm $p = (x, y, z)$ thì các điểm có dạng $(x / z, y / z, 1)$ (hoặc với $z = 0$ thì điểm $(x / y, 1, 0)$, tương tự với $x = 0$ hoặc $y = 0$) sẽ đều biểu diễn cùng một điểm. Như vậy một điểm được xác định không phục thuộc vào cả 3 thành phần $x, y, z$ mà chỉ phụ thuộc vào 2 trong số 3. Ta nói mỗi điểm có degrees of freedom là 2 (dof = 2). Tương tự một đường thẳng cũng có dof 2.
Các thành phần khác như vector nhiều chiều hoặc ma trận sẽ có dof khác nhau.
Dof cũng là một yếu tố quan trọng, vì để xác định được một thành phần có dof là n thì ta cần biết n yếu tố khác nhau liên quan đến nó, như đường thẳng ta cần biết 2 điểm nó đi qua, ...

## Giao điểm của hai đường thẳng, đường thẳng qua 2 điểm.
Hai đường thẳng $l_1$ và $l_2$ sẽ có giao điểm $x = l_1 \times l_2$.
> Thật vậy, $l_1(l_1 \times l_2) = 0$ và $l_2(l_1 \times l_2) = 0$, do vector $l_1 \times l_2$ trong không gian cùng song song với cả $l_1$ và $l_2$. Như vậy $l_1$ và $l_2$ đều đi qua điểm $l_1 \times l_2$

Hai điểm $p_1$ và $p_2$ có sẽ có đường thẳng $l = p_1 \times p_2$ cùng đi qua chúng.
> Cũng như trên, do $p_1.(p_1 \times p_2) = 0$ và $p_2.(p_1 \times p_2) = 0$. Như vậy $p_1$ và $p_2$ đều thuộc đường thằng $p_1 \times p_2$

Với điểm và đường thẳng ở vô cùng.
- Tập hợp các điểm ở vô cùng tạo thành đường thẳng ở vô cùng $(0, 0, 1)^T$
> Thật vậy $(a, b, 0)^T(0, 0, 1) = 0$.
- Mọi đường thẳng $l = (a, b, c)$ đều giao với đường thẳng $(0, 0, 1)^T$ tại điểm $(b, -a, 0)^T$

## Tính đối lập (duality)
Ta có thể đảo vai trò của điểm và đường thẳng cho nhau. Từ việc chúng đều là vector 3 chiều, đến việc tìm giao điếm/đường thẳng qua 2 điểm. Đây gọi là nguyên tắc đôi lập (duality principle).
> Trong hình học xạ ảnh, mỗi định lý liên quan đến đương thẳng và điểm đều tồn tại một định lý khác mà điểm và đường thẳng đảo vai trò cho nhau.

## Đường conic và phương trình đường conic
Các đường conic cơ bản gồm đường hyperbola, ellipse và parabola.
Phương trình conic là đa thức bậc 2 có dạng:
$$ax^2 + bxy + cx^2 + dx + ey + f = 0$$
Ta có thể "đồng nhât hóa nó bằng cách thay $x$ bởi $x/z$ và $y$ bởi $y/z$, ta được phương trình:
$$ax^2 + bxy + cx^2 + dxz + eyz + fz^2 = 0$$

Để dễ dàng cho việc tính toán ta chuyển phương trình trên về dạng ma trận:
$$x^TCx = 0$$
Với ma trận $C$ gồm các hệ số:
$$C = \begin{bmatrix}
a   & b/2 & d/2 \\
b/2 & c   & e/2 \\
d/2 & e/2 & f
\end{bmatrix}$$

Nhận xét:
- Ma trận này đối xứng them đường chéo chính.
- Ma trận trên bao gồm 6 hệ số, và vì ta có thể nhân chia ma trận với bất cứ số khác 0 nào nên nó có dof 5. Nói cách khác, mỗi đường conic xác định bởi 5 điểm khác nhau.
- Đường thẳng $l = Cx$ (với $x \in C$) là tiếp tuyến của $C$ tại $x$.
- Nếu rank của ma trận $C$ nhỏ hơn 3, conic $C$ sẽ [suy biến thành điểm/đường thẳng](https://en.wikipedia.org/wiki/Degenerate_conic).

**Dual coninc**: Conic trên còn được gọi là *point conic* vì nó xác định trên điểm. Áp dụng quy tắc đối lập, với mỗi point conic C sẽ có loại một conic $C^*$ khác xác định trên đường thẳng, gọi là *dual conic* hoặc *line conic*. Với mỗi đường thẳng $l$ là tiếp tuyến của $C$ thì thỏa mãn $l^TC^*l = 0$. Với mỗi ma trận khả nghịch $C$ thì $C^* = C^T$

**Conic tạo bởi 2 đường thẳng**
$$C = lm^T + ml^T$$
Là conic quy biến gồm các điểm thuộc một trong hai đường thẳng.
> Thật vậy với mỗi điểm $x$ thỏa mãn $l^Tx = 0$ thì $x^TCx = (x^Tl)(m^Tx) + (x^Tm)(l^Tx) = 0$.

Ngoài ra ta còn có dual conic tạo bở hai điểm, conic gồm tất cả đường thẳng đi qua một trong hai điểm đó.

---