# VIETNAMESE FAKE NEWS DATASET - VFND

[![DOI](https://zenodo.org/badge/134866350.svg)](https://zenodo.org/badge/latestdoi/134866350) [![Hits-of-Code](https://hitsofcode.com/github/thanhhocse96/vfnd-vietnamese-fake-news-datasets)](https://hitsofcode.com/view/github/thanhhocse96/vfnd-vietnamese-fake-news-datasets) ![GitHub contributors](https://img.shields.io/github/contributors/thanhhocse96/vfnd-vietnamese-fake-news-datasets.svg) ![GitHub](https://img.shields.io/github/license/thanhhocse96/vfnd-vietnamese-fake-news-datasets.svg)

VFND là bộ dataset về các tin tức giả bằng ngôn ngữ tiếng Việt được tập hợp trong khoảng thời gian từ 2017 đến 2019 (năm hoàn thành luận văn của các tác giả), các tin tức được đưa vào đây được phân loại thật giả dựa trên một số nguồn tin, tham chiếu chéo đến các nguồn tin được dẫn hoặc được phân loại bởi cộng đồng.

Nếu muốn sử dụng, mời các bạn vui lòng liên hệ đến email: [thanh.hoquang@pm.me](mailto:thanh.hoquang@pm.me), và vui lòng dẫn nguồn của bộ dữ liệu này trong bài viết của bạn \(Xem phần 6 để copy BibTex dễ dàng\):

`[1]Ho Quang Thanh and ninh-pm-se, “thanhhocse96/vfnd-vietnamese-fake-news-datasets: Tập hợp các bài báo tiếng Việt và các bài post Facebook phân loại 2 nhãn Thật & Giả (228 bài)”. Zenodo, 27-Feb-2019.`

Nhằm xây dựng bộ dataset chi tiết hơn (có thể gọi là version 2) về tin tức giả Tiếng Việt, chúng tôi mong các bạn có thể báo cáo các tin tức giả các bạn vô tình đọc được qua đường dẫn sau [http://bit.ly/fake-news-report-zefro](http://bit.ly/fake-news-report-zefro) (Khi các bạn báo cáo, vui lòng dùng thêm link wayback machine để chúng tôi có thể cập nhật nếu như trang tin giả được các cơ quan hữu trách dọn dẹp). Các bạn có thể tham khảo một số content về tin tức giả được chúng tôi cập nhật trên [ZeFro blog](https://zefro.wordpress.com/portfolio/fake-news-detection-nhan-dang-tin-tuc-gia/)

**Dự án xin ngừng cập nhật với lý do:** trong một môi trường tin tức chỉ có 1 kiểu tường thuật được cấp phép, quản lý và kiểm duyệt, việc nhận dạng tin tức giả trở nên không cần thiết. 

## 1. Giới thiệu tổng quan và các chủ đề tin tức

Cấu trúc tên của 1 file bao gồm: `VFND_{Source}_{Label}_{Number}.json`.

Trong đó

- `{Source}`:
  - `Ac` - nguồn bài báo từ các trang tin tức;
  - `So` - Nguồn từ các bài viết của người dùng trên mạng xã hội Facebook, Twitter, YouTube... có tính chất như nguồn tin tức.
- `{Label}` thuộc tập `{“Fake”, “Real”}`

### 1.1 Giới hạn các chủ đề tin tức trong tập dữ liệu:

1. Các tin tức sử dụng trong bộ dataset đều là tin tức tường thuật về 1 sự kiện. Lý do: Để có thể kiểm tra chéo giữa các nguồn tin để xác định được tin tức thật hoặc giả trong trường hợp mà cộng đồng chưa hỗ trợ phân loại tin tức.

2. Các chủ đề mà bộ dataset tập trung là: Thể thao, Văn hóa, Xã hội, Kinh tế, Pháp luật, Y tế, ... Các tin tức sẽ được kiểm tra chéo về nguồn gốc, nội dung, sự kiện để xác định thật và giả

3. Một số chú ý: Một số tin tức sẽ được nhóm mặc định là tin giả: tin tức có tính chất mê tín, dị đoan; tin tức không xác nhận được nguồn tin; tin tức dựa trên những nguồn tin, kiến thức, học thuyết, luận thuyết được khoa học công nhận là sai lầm

### 1.2. Cách thức lấy dữ liệu

Các dữ liệu tin tức và nguồn dữ liệu của bộ dataset sẽ được trình bày trong các file README.md đi theo từng thư mục phân loại. Trong đó nội dung các file sẽ đưa ra nguồn tin tức và cách mà nhóm phân loại tin tức đó là giả.

Nhóm sử dụng thư viện: [news-please](https://github.com/fhamborg/news-please)

## 2. Mô tả các thành phần thư mục trong bộ dữ liệu

### 2.1 [_Fake\_Real\_Dataset_](Fake_Real_Dataset)

[Fake_Real_Dataset](Fake_Real_Dataset): Tập dữ liệu được phân loại dựa trên 2 nhãn [Fake](Fake_Real_Dataset/Fake/) và [Real](Fake_Real_Dataset/Real) trong đó với mỗi nhãn tương ứng với một thư muc, trong từng thư muc sẽ được phân loại thành 2 nhóm: [Article_Contents](Fake_Real_Dataset/Article_Contents): tập hợp các bài báo đã được phân loại trong nhãn  và [Social_Contents](Facebook): tập hợp các Facebook post đã được phân loại.

```
Fake_Real_Dataset
└───Fake
    └───Article_Contents
    └───Social_Contents
└───Real
    └───Article_Contents
    └───Social_Contents
└───Misleading
    └───Article_Contents
    └───Social_Contents
```

### 2.3. [_Tools_](Tools): 
Các công cụ và thử nghiệm hỗ trợ việc lấy dữ liệu tin tức

### 2.4. [_Dictionaries_](Dictionaries)

Một số bộ từ điển hỗ trợ (nếu các nhóm sử dụng các thuật toán cổ điển để khảo sát). Đọc thêm chi tiết tại [README.md](Dictionaries/README.md)

### 2.5. [_CSV_](CSV): Các file CSV được trích xuất từ bộ dữ liệu

## 3. Các thư viện được sử dụng

1. NewsPlease
2. BeautifulSoup
3. Fake UserAgent

## 4. Các tác giả

Xem thêm trong [contributors](https://github.com/thanhhocse96/vfnd-vietnamese-fake-news-datasets/graphs/contributors)

## 5. Tham khảo thêm

## 6. Dẫn nguồn BibTex:

```TeX
@misc{ho_quang_thanh_2019_2578917,
  author       = {Ho Quang Thanh and
                  ninh-pm-se},
  title        = {{thanhhocse96/vfnd-vietnamese-fake-news-datasets:
                   Tập hợp các bài báo tiếng Việt và các bài post
                   Facebook phân loại 2 nhãn Thật \& Giả (228 bài)}},
  month        = feb,
  year         = 2019,
  doi          = {10.5281/zenodo.2578917},
  url          = {https://doi.org/10.5281/zenodo.2578917}
}
```
