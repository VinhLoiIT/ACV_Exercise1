# Báo cáo bài tập 1

# Thông tin sinh viên
MSSV: 1612348
Họ và tên: Lý Vĩnh Lợi
Email: vinhloiit1327@gmail.com

# Nội dung

## Bảng số liệu kết quả

| Version | Changes | Test Accuracy |
| --- | --- | --- |
| [8][v8] | Quay lại version [5], thêm 2 lớp Gated, 2 lớp Gated max pooling 1 lần | **0.9330** |
| [7][v7] | Thêm 1 lớp Conv2D sau Version 6 | 0.9278 |
| [6][v6] | Thêm 1 lớp Conv2D sau 3 lớp gate | 0.9214 |
| [5][v5] | <lu><li>Bỏ bớt Batch Norm giữa các layer</li><li>Gộp 2 lớp FC(64), FC(32) thành 1 lớp FC(128)</li></lu> | 0.9321 |
| [4][v4] | <lu><li>Augmentation bằng cách thêm nhiễu Gauss (mean, std) = (0, 0.1) (do ảnh đã norm từ 0..255 thành 0..1)</li><li>Thêm 1 cổng Gated</li></lu> | 0.9223 |
| [3][v3] | Chuyển mô hình sang Gated CNN (thêm cơ chế cổng). Dùng 2 cổng | 0.9285 |
| [2][v2] | Tăng thêm 1 lớp Conv2D, sử dụng BatchNormalization | 0.9112 |
| [1][v1] | Sử dụng CNN 1 lớp cơ bản dựa trên [tutorial] | 0.9159 |

[v1]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21110871
[v2]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21217665
[v3]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21219669
[v4]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21221321
[v5]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21221727
[v6]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21223135
[v7]: https://www.kaggle.com/vinhloiit1327/exercise-fashionmnist?scriptVersionId=21305908
[v8]: https://www.kaggle.com/vinhloiit1327/fork-of-exercise-fashionmnist-6c1608?scriptVersionId=21343828
[tutorial]: https://www.kaggle.com/pavansanagapati/a-tutorial-cnn-model-fashion-mnist

## Nhận xét kết quả
Mô hình cơ bản: **0.9159**
Mô hình tốt nhất: **0.9330**

- Mô hình CNN về cơ bản đã chạy tốt với tập dữ liệu (độ chính xác trên tập test > 90%) dù chỉ gồm 1 số lớp đơn giản
- Cải tiến mô hình bằng cách thêm cổng tăng độ chính xác thêm 0.01, tức tăng thêm 1%
- Augmentation bằng cách thêm nhiễu Gauss không tăng thêm độ chính xác nhiều. Tuy nhiên làm mô hình nặng thêm bằng cách thêm các lớp Gated tăng độ chính xác lên thêm 0.01, tức thêm 1%

## Đánh giá
Qua kết quả trên cho thấy, cơ chế cổng giúp tăng độ chính xác hơn sơ với mô hình CNN truyền thống.

Ý tưởng ban đầu là sử dụng cổng (hàm kích hoạt sigmoid) sẽ giúp loại bỏ bớt nhiễu/đặc trưng ảnh hưởng xấu đến kết quả. Nó loại được nhiễu có khả năng là do hàm kích hoạt sigmoid có giá trị thuộc $[0..1]$ tương ứng xác suất/độ mạnh yếu của đặc trưng
Biểu thức toán:
$$\mathbf{y}=g(\mathbf{x}).\mathbf{x}$$
Trong đó:
- $\mathbf{x}$ là đặc trưng input của lớp hiện tại
- $\mathbf{y}$ là đặc trưng output của lớp hiện tại
- $\mathbf{.}$ là toán tử nhân từng phần tử (element-wise)
- $g(\mathbf{x})$ là hàm convolution với hàm kích hoạt sigmoid
