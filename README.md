# ACV_Exercise1
Applied Computer Vision Project 1

# Changelog
- Version 7:
  - Thêm 1 lớp Conv2D sau Version 6
  - Kết quả: 0.9277999997138977

- Version 6:
  - Thêm 1 lớp Conv2D sau 3 lớp gate
  - Kết quả: 0.9214000105857849

- Version 5:
  - Bỏ bớt Batch Norm giữa các layer
  - Gộp 2 lớp FC(64), FC(32) thành 1 lớp FC(128)
  - Kết quả: 0.9320999979972839

- Version 4:
  - Augmentation bằng cách thêm nhiễu Gauss (mean, std) = (0, 0.1) (do ảnh đã norm từ 0..255 thành 0..1)
  - Thêm 1 cổng Gated
  - Kết quả: 0.9222999811172485

- Version 3:
  - Chuyển mô hình sang Gated CNN (thêm cơ chế cổng). Dùng 2 cổng
  - Kết quả: 0.9284999966621399

- Version 2:
  - Tăng thêm 1 lớp Conv2D, sử dụng BatchNormalization
  - Kết quả: 0.9111999869346619

- Version 1:
  - Sử dụng CNN 1 lớp cơ bản dựa trên [tutorial](https://www.kaggle.com/pavansanagapati/a-tutorial-cnn-model-fashion-mnist)
  - Kết quả: 0.9159
