## Hệ thống giao dịch tự động trên sàn chứng khoán Thành Phố Hồ Chí Minh sử dụng phương pháp học tăng cường
**1. Giới thiệu**

  Những năm gần đây, phong trào đầu tư tài chính mà cụ thể là đầu tư chứng khoán phát triển mạnh mẽ ở Việt Nam. Số lượng tài khoản mở mới trung bình hằng tháng đã tăng từ mức 20,000 năm 2017 lên mức trên 110,000 năm 2021 [1]. Thanh khoản trung bình của hệ thống cũng tăng từ mức 4,000 tỉ đồng mỗi phiên giao dịch năm 2017 lên mức 30,000 tỉ đồng năm 2021. Những năm sắp tới, thị trường chứng khoán được dự báo bùng nổ hơn nữa vì tỉ lệ người dân đầu tư chứng khoán của Việt Nam vẫn còn rât nhỏ so với những nước phát triển. Tỉ lệ này ở Việt Nam là 3% (tháng 5 năm 2021) so với mức gần 50% ở một số nước phát triển. Như vậy, đầu tư chứng khoán là lĩnh vực còn rất nhiều tiềm năng phát triển ở Việt Nam.
  
  Một trong những đặc điểm của việc đầu tư chứng khoán là giá của các cổ phiếu thay đổi rất nhanh và phức tạp. Hàng nghìn lệnh mua và bán được xử lý mỗi giây dẫn đến việc giá cổ phiếu có thể thay đổi lớn (+/- 7% trên sàn HOSE) trong khoản thời gian 1 giây. Việc hàng triệu nhà đầu tư cùng lúc ra quyết định mua bán dựa vào nhiều nguồn thông tin khác nhau (báo điện tử, diễn đàn mạng xã hội) dẫn đến việc dự đoán giá cổ phiếu trong ngắn hạn gần như là không thể đối với nhà đầu tư.
  
  Trước tình hình đó, những nhà đầu tư tổ chức và các công ty chứng khoán đã xây dựng các hệ thống mua bán tự động dựa vào 1 số chỉ báo. Tuy nhiên các chỉ báo này thường rất thô sơ, ví dụ so sánh giá cổ phiếu hiện tại với một giá cố định được đặt trước hoặc chỉ số dựa vào giá cổ phiếu trong quá khứ (ví dụ chỉ số sức mạnh tương đối RSI, đường trung bình động MA, dải Bollinger BB, ...). Đặc điểm của những chỉ số này là chỉ quan tâm đến giá của 1 cổ phiếu cụ thể trong quá khứ mà không kết hợp thông tin từ việc thay đổi giá của các cổ phiếu khác và thông tin từ báo điện tử và mạng xã hội. Hệ thống mua bán tự động từ đó cũng chỉ ra quyết định mua bán độc lập mà không ra quyết định dựa trên tổng thể các mã cổ phiếu và số tiền hiện tại (quản lý danh mục - porfolio management). 
  
  Về mặt học thuật, phương pháp học tăng cường đã chứng minh được hiệu quả trong việc ra quyết định trong thời gian ngắn để đạt được lợi ích tối đa trong dài hạn, rất phù hợp trong ứng dụng đầu tư chứng khoán tự động. Ramit Sawhney và Arnav Wadhwa đã ứng dụng phương pháp học tăng cường để thực nghiệm mua bán chứng khoán trên sàn NASDAQ Shanghai, Shenzhen, Hong Kong [2] với kết quả tích cực (tốt hơn so với các phương pháp khác trong quá khứ). Mục tiêu của đề tài này là áp dụng phương pháp học tăng cường để xây dựng và đánh giá hệ thông giao dịch tự động ở thị trường chứng khoán Việt Nam.
  
**2. Mục tiêu của đề tài**

  Mục tiêu tổng quát: xây dựng và đánh giá hệ thống giao dịch tự động trên thị trường chứng khoán Việt Nam với mục tiêu lợi nhuận trong trung và dài hạn (trên 3 tháng) cao hơn lãi suất ngân hàng (6%/năm) và tăng trưởng của chỉ số VN-Index trong cùng thời gian.
  
  Mục tiêu cụ thể:
  - Hiểu rõ và lặp lại được các phương pháp đề cập trong tài liệu tham khảo [2] cũng như các phương pháp khác được xây dựng cho thị trường chứng khoán Việt Nam [3-8].
  - Xây dựng hệ thống dữ liệu của tin tức, bài đăng trên mạng xã hội và giá cổ phiếu ở Việt Nam trong quá khứ và môi trường gia dịch ảo sử dụng dữ liệu thu thập được.
  - Xây dựng hệ thống giao dịch ứng dụng phương pháp học tăng cường với dữ liệu quá khứ.
  - Thử nghiệm hệ thống với giao dịch tự động trực tiếp trên sàn HOSE
  
**3. Nội dung nghiên cứu**

  Đề tài nghiên cứu bao gồm những nội dung sau:
  - Đọc và hiểu rõ các tài liệu trong phần tham khảo.
  - Tập hợp dữ liệu liên quan từ các tài liệu tham khảo.
  - Xây dựng code dựa vào tài liệu tham khảo hoặc dựa vào code của các tài liệu tham khảo (nếu có sẵn).
  - Đánh giá lại các phương pháp trong phần tài liệu tham khảo.
  - Crawl dữ liệu từ các trang báo điện tử và các trang mạng xã hội liên quan đến lĩnh vực chứng khoán (https://cafef.vn, https://tinnhanhchungkhoan.vn/, https://vietstock.vn/, https://ndh.vn/, https://www.thesaigontimes.vn/, diễn đàn facebook: Diễn đàn chứng khoán Việt Nam, Chứng khoán lướt sóng thần).
  - Kết hợp dữ liệu crawl được với dữ liệu đã có từ tài liệu tham khảo, sắp xếp theo mã chứng khoán và thời điểm xuất hiện.
  - Xây dựng môi trường gia dịch chứng khoán ảo dựa theo dữ liệu đã tổ chức lại.
  - Train agent trong môi trường chứng khoán ảo.
  - Train agent và đánh giá việc giao dịch thực tế trên sàn HOSE.
  - Viết báo cáo tổng kết.

**4. Kết quả, sản phẩm dự kiến**

  - Dữ liệu từ báo điện tử, mạng xã hội và giá chứng khoán được phân loại theo mã chứng khoán và sắp xếp theo thứ tự thời gian.
  - Môi trường giao dịch chứng khoán ảo dùng để huấn luyện agent theo phương pháp học tăng cường.
  - Ứng dụng giao dịch chứng khoán tự động trên sàn HOSE.
  - Báo cáo tổng kết.

**5. Kế hoạch thực hiện**

  - Tuần 1-4: Đọc và hiểu rõ các tài liệu trong phần tham khảo.
  - Tuần 5-6: Tập hợp dữ liệu liên quan từ các tài liệu tham khảo.
  - Tuần 7-10: Xây dựng code dựa vào tài liệu tham khảo hoặc dựa vào code của các tài liệu tham khảo (nếu có sẵn).
  - Tuần 11-12: Đánh giá lại các phương pháp trong phần tài liệu tham khảo.
  - Tuần 1-12: Crawl dữ liệu từ các trang báo điện tử và các trang mạng xã hội liên quan đến lĩnh vực chứng khoán (https://cafef.vn, https://tinnhanhchungkhoan.vn/, https://vietstock.vn/, https://ndh.vn/, https://www.thesaigontimes.vn/, diễn đàn facebook: Diễn đàn chứng khoán Việt Nam, Chứng khoán lướt sóng thần).
  - Tuần 13-16: Kết hợp dữ liệu crawl được với dữ liệu đã có từ tài liệu tham khảo, sắp xếp theo mã chứng khoán và thời điểm xuất hiện.
  - Tuần 17-20: Xây dựng môi trường gia dịch chứng khoán ảo dựa theo dữ liệu đã tổ chức lại.
  - Tuần 21-24: Train agent trong môi trường chứng khoán ảo.
  - Tuần 25-32: Train agent và đánh giá việc giao dịch thực tế trên sàn HOSE.
  - Tuần 28-36: Viết báo cáo tổng hợp  

**6. Trích dẫn**

  [1] https://vneconomy.vn/gan-114-ngan-tai-khoan-chung-khoan-mo-moi-trong-thang-5.htm (2021)
  [2] https://www.aclweb.org/anthology/2021.naacl-main.316.pdf (2021)
  [3] Dương Minh Đức, Hệ dự đoán chỉ số VN - INDEX dựa trên mô hình học sâu, Nguyễn Việt Phương (2021)
  [4] Dương Minh Đức, Ứng dụng SVM và chuỗi thời gian dự đoán xu hướng thị trường chứng khoán Việt Nam, Trần Quốc Bảo (2017)
  [5] Võ Đình Bảy, Áp dụng phương pháp lai giữa thuật toán tối ưu bầy đàn và hồi qui vécto hỗ trợ trong dự đoán giá chứng khoán A hybrid PSO-SVR approach for Vietnam stock price prediction on market, Lê Đỗ Minh Nga (2017)
  [6] Đỗ Phúc, Ứng dụng luật kết hợp để khám pháp mối quan hệ giữa các tỉ số tài chính và giá chứng khoán, Huỳnh Văn Trận (2016)
  [7] Dương Minh Đức, Dự báo xu hướng chứng khoán dựa vào tin tức tài chính tại sàn giao dịch TPHCM (HOSE), Huỳnh Đức Huy (2015)
  [8] Hoàng Văn Kiếm, Ứng dụng text mining dự báo thị trường chứng khoán Việt Nam, Phạm Xuân Dũng (2015)
