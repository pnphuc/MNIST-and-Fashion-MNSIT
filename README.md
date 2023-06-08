#ANN


<a name="_toc131774612"></a>**Chương 1: Tập dữ liệu MNIST**

<a name="_toc131774613"></a>**1. Giới thiệu**

\- MNIST là tập hợp các chữ số viết tay từ số 0 đến 9.

\- Nó có một tập huấn luyện gồm 60.000 hình ảnh và 10.000 hình ảnh thử nghiệm được phân loại thành các danh mục hoặc nhãn tương ứng.

\- Để sử dụng bộ dữ liệu MNIST trong Keras, một API được cung cấp để tự động tải xuống và trích xuất hình ảnh cũng như nhãn.


<a name="_toc131774628"></a>**5. Đánh giá và đề xuất best practice:**

<a name="_toc131774629"></a>**5.1 Đánh giá**

\- Thời gian train model được đánh giá ở google colab với bản free.

|**STT**|**Loại**|**Độ chính xác**|**Thời gian train model**|
| :-: | :-: | :-: | :-: |
|**1**|Số lượng node ẩn là 512|97\.9%|43\.3 giây|
|**2**|Số lượng node ẩn là 100|97\.8%|32\.5 giây|
|**3**|Số lượng node ẩn là 200|98\.1%|34\.1 giây|
|**4**|Số lượng node ẩn là 500|98\.2%|32\.6 giây|
|**5**|Số lượng lớp ảnh là 2|98\.3%|44\.2 giây|
|**6**|Số lượng lớp ảnh là 3|98\.2%|43 giây|

\- Dựa vào bảng trên thấy được kết quả cho thấy với số lượng lớp ảnh là 2 cho kết quả tốt nhất, với số lượng lớp ẩn lần lượt là 512 và 256. Nhưng để cho được kết quả tốt nhất thì thời gian train của 2 lớp ảnh lâu hơn các loại khác ở trên bảng.

\- Tổng quan, độ chính xác cho ra của mỗi loại khá đồng đều độ sai số chỉ ở mức ±2. Thời gian train model thì phụ thuộc vào số lượng node ẩn và lớp ảnh rất nhiều.

<a name="_toc131774630"></a>**5.2 Đề xuất best practice:**

\- Dựa vào bảng số sánh ở trên thì thấy được best practice vừa là về độ chính xác vừa là về thời gian train model là loại số lượng node ẩn là 500 với 1 lớp ảnh.

\- Kết quả đạt được ở practice này với độ chính xác là 98.2% và thời gian train là 32.6 giây.






**

<a name="_toc131774631"></a>**Chương 2: Tập dữ liệu Fashion MNIST**

<a name="_toc131774632"></a>**1. Giới thiệu**

\- Fashion-MNIST là tập dữ liệu gồm các hình ảnh bài viết của Zalando bao gồm tập huấn luyện gồm 60.000 ví dụ và tập kiểm tra gồm 10.000 ví dụ. 

\- Mỗi ví dụ là một hình ảnh thang độ xám 28x28, được liên kết với nhãn từ 10 lớp.

\- Zalando dự định Fashion-MNIST sẽ đóng vai trò thay thế trực tiếp cho bộ dữ liệu MNIST ban đầu để đo điểm chuẩn cho các thuật toán machine learning.


<a name="_toc131774647"></a>**5. Đánh giá và đề xuất best practice:**

<a name="_toc131774648"></a>**5.1 Đánh giá**

\- Thời gian train model được đánh giá ở google colab với bản free.

|**STT**|**Loại**|**Độ chính xác**|**Thời gian train model**|
| :-: | :-: | :-: | :-: |
|**1**|Số lượng node ẩn là 512|89\.5%|32\.3 giây|
|**2**|Số lượng node ẩn là 100|88\.2%|34\.6 giây|
|**3**|Số lượng node ẩn là 200|88\.7%|43\.6 giây|
|**4**|Số lượng node ẩn là 500|89\.5%|44\.1 giây|
|**5**|Số lượng lớp ảnh là 2|89\.1%|36 giây|
|**6**|Số lượng lớp ảnh là 3|89\.2%|44\.3 giây|

\- Dựa vào bảng trên thấy được kết quả cho thấy với số lượng node ẩn là 512 và 1 lớp ảnh cho ra kết quả chính xác nhất với độ chính xác là 89.5% và thời gian train model cũng rất nhanh với thời gian nhanh nhất trong 6 loại ở trên

\- Tổng quan, độ chính xác cho ra của mỗi loại gần như là xêm xêm nhau với độ sai số là ±3.

<a name="_toc131774649"></a>**5.2 Đề xuất best practice:**

\- Dựa vào bảng số sánh ở trên thì thấy được best practice vừa là về độ chính xác vừa là về thời gian train model là loại số lượng node ẩn là 512 với 1 lớp ảnh

\- Thời gian train model ở practice này nhanh nhất và cho ra độ chính xác cũng đúng nhất với 89.5%.


