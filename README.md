# ACV_Exercise1
Applied Computer Vision Project 1

# Changelog

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
