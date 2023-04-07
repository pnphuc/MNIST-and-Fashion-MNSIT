
<a name="_toc131774611"></a>**GIỚI THIỆU**

1. **Sinh viên**
- Họ và tên: Phùng Nghĩa Phúc
- MSV: 20127284
- Lớp: 20TGMT01
- Môn học: Đồ hoạ ứng dụng
1. **Chủ đề**
- Thiết kế mạng neural network 3 lớp với tập dữ liệu MNIST và Fashion MNIST  

<a name="_toc131774612"></a>**Chương 1: Tập dữ liệu MNIST**

<a name="_toc131774613"></a>**1. Giới thiệu**

\- MNIST là tập hợp các chữ số viết tay từ số 0 đến 9.

\- Nó có một tập huấn luyện gồm 60.000 hình ảnh và 10.000 hình ảnh thử nghiệm được phân loại thành các danh mục hoặc nhãn tương ứng.

\- Để sử dụng bộ dữ liệu MNIST trong Keras, một API được cung cấp để tự động tải xuống và trích xuất hình ảnh cũng như nhãn.

<a name="_toc131774614"></a>**1.1. Thư viện sử dụng**

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

%matplotlib inline

import tensorflow as tf

from keras.datasets import mnist

from keras.models import Sequential

from keras.layers import Dense

from keras.utils import to\_categorical

from keras import layers

from keras import models

<a name="_toc131774615"></a>**1.2. MNIST dataset**

\- Đếm số lượng labels: train và test duy nhất trong dataset:

Train labels:  {0: 5923, 1: 6742, 2: 5958, 3: 6131, 4: 5842, 5: 5421, 6: 5918, 7: 6265, 8: 5851, 9: 5949}

Test labels:  {0: 980, 1: 1135, 2: 1032, 3: 1010, 4: 982, 5: 892, 6: 958, 7: 1028, 8: 974, 9: 1009}



<a name="_toc131774616"></a>**1.3. Visualization data với 25 mẫu từ train dataset**

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.005.png)

<a name="_toc131774617"></a>**2. Thiết kế mạng neural network 3 lớp: 1 lớp input, 1 lớp ẩn và 1 lớp output**

<a name="_toc131774618"></a>**2.1. Thiết kế**

\- Thiết kế mạng với:

\- Lớp input với size ảnh đầu vào là 28 \* 28 = 784

`	`- Lớp ẩn với 512 units

`	`- Lớp output với 10 units

\- Để train model thì sử dụng với chỉ số epochs là 20 vầ validation\_split = 0.1

<a name="_toc131774619"></a>**2.2 Kết quả**

![Table

Description automatically generated with medium confidence](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.006.png)

<a name="_toc131774620"></a>**2.3 Đánh giá model**

\- Dựa vào kết quả train ở trên thì sử dụng evaluate() method để tính được phần trăm độ chính xác.

\- Độ chính xác ở tập dữ liệu MNSIT ở đây là **97.9%**

<a name="_toc131774621"></a>**3. Thực nghiệm số lượng node ẩn với: 100, 200 và 500 trên tập dataset**

<a name="_toc131774622"></a>**3.1 Với số lượng node ẩn là 100**

\- Kết quả sau khi test: 

![Text

Description automatically generated](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.007.png)

\- Đánh giá độ chính xác: Phần trăm độ chính xác với số lượng node ẩn 100 là **97.8%**

<a name="_toc131774623"></a>**3.2 Với số lượng node ẩn là 200**

**-** Kết quả:

![Text

Description automatically generated with low confidence](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.008.png)

\- Đánh giá phần trăm chính xác với số lượng node ẩn 200 là **98.1%**

<a name="_toc131774624"></a>**3.3 Với số lượng node ẩn là 500**

\- Kết quả:

![Text

Description automatically generated with medium confidence](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.009.png)

\- Đánh giá phần trăm chính xác với số lượng node ẩn 500 là **98.2%**

<a name="_toc131774625"></a>**4. Tăng số lượng lớp ảnh lên 2 và 3**

<a name="_toc131774626"></a>**4.1 Với số lượng lớp ảnh là 2**

\- Kết quả: 

![Text

Description automatically generated with medium confidence](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.010.png)

\- Đánh giá phần trăm chính xác: 98.3%

<a name="_toc131774627"></a>**4.2 Với số lượng lớp ảnh là 3**

\- Kết quả: 

![Text

Description automatically generated](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.011.png)

\- Đánh giá phần trăm chính xác: 98.2%

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

<a name="_toc131774633"></a>**1.1. Thư viện sử dụng**

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

%matplotlib inline

import tensorflow as tf

from keras.datasets import mnist

from keras.models import Sequential

from keras.layers import Dense

from keras.utils import to\_categorical

from keras import layers

from keras import models

<a name="_toc131774634"></a>**1.2. MNIST dataset**

\- Đếm số lượng labels: train và test duy nhất trong dataset:

Train labels:  {0: 6000, 1: 6000, 2: 6000, 3: 6000, 4: 6000, 5: 6000, 6: 6000, 7: 6000, 8: 6000, 9: 6000}

Test labels:  {0: 1000, 1: 1000, 2: 1000, 3: 1000, 4: 1000, 5: 1000, 6: 1000, 7: 1000, 8: 1000, 9: 1000}

<a name="_toc131774635"></a>**1.3. Visualization data với 25 mẫu từ train dataset**

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.012.png)

<a name="_toc131774636"></a>**2. Thiết kế mạng neural network 3 lớp: 1 lớp input, 1 lớp ẩn và 1 lớp output**

<a name="_toc131774637"></a>**2.1. Thiết kế**

\- Thiết kế mạng với:

\- Lớp input với size ảnh đầu vào là 28 \* 28 = 784

`	`- Lớp ẩn với 512 units

`	`- Lớp output với 10 units

\- Để train model thì sử dụng với chỉ số epochs là 20 và validation\_split = 0.1

<a name="_toc131774638"></a>**2.2 Kết quả**

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.013.png)

<a name="_toc131774639"></a>**2.3 Đánh giá model**

\- Dựa vào kết quả train ở trên thì sử dụng evaluate() method để tính được phần trăm độ chính xác.

\- Độ chính xác ở tập dữ liệu MNSIT ở đây là **89.5%**

<a name="_toc131774640"></a>**3. Thực nghiệm số lượng node ẩn với: 100, 200 và 500 trên tập dataset**

<a name="_toc131774641"></a>**3.1 Với số lượng node ẩn là 100**

\- Kết quả sau khi test: 

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.014.png)

\- Đánh giá độ chính xác: Phần trăm độ chính xác với số lượng node ẩn 100 là **88.2%**

<a name="_toc131774642"></a>**3.2 Với số lượng node ẩn là 200**

**-** Kết quả:

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.015.png)

\- Đánh giá phần trăm chính xác với số lượng node ẩn 200 là **88.7%**

<a name="_toc131774643"></a>**3.3 Với số lượng node ẩn là 500**

\- Kết quả:

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.016.png)

\- Đánh giá phần trăm chính xác với số lượng node ẩn 500 là **89.5%**

<a name="_toc131774644"></a>**4. Tăng số lượng lớp ảnh lên 2 và 3**

<a name="_toc131774645"></a>**4.1 Với số lượng lớp ảnh là 2**

\- Kết quả: 

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.017.png)

\- Đánh giá phần trăm chính xác: **89.1%**

<a name="_toc131774646"></a>**4.2 Với số lượng lớp ảnh là 3**

\- Kết quả: 

![](Aspose.Words.c1d98cae-0ecc-450e-b411-423bf3dd70ef.018.png)

\- Đánh giá phần trăm chính xác: **89.2%**

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



15

