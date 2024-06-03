## Hệ thống gợi ý bài hát dựa trên thói quen của người dùng bằng phương pháp K-means

Hiện nay có rất nhiều ứng dụng nghe nhạc ra đời như Spotify, Apple Music,… do đó người dùng có nhiều lựa chọn hơn trong việc chọn ra cho mình danh sách những bài hát yêu thích từ những trang web đó. Bên cạnh đó, vẫn có nhiều người dùng có thói quen tải những bài nhạc về để nghe ngoại tuyến, việc này đã trở thành thói quen và đem lại sự thuận tiện cho họ. Tuy nhiên, hiếm có người dùng nào có thể tạo ra một danh sách gợi ý các bài hát cho những lần tải về tiếp theo của mình. Chính vì thế, chúng tôi mong muốn giới thiệu một hệ thống gợi ý âm nhạc dựa trên thuật toán K-means clustering.

Hệ thống của chúng tôi sử dụng dữ liệu từ thói quen nghe nhạc của người dùng rồi chia họ thành từng nhóm người dùng khác nhau và gợi ý cho những nhóm đó về những bài hát có chủ đề, thể loại, nghệ sĩ, xuất xứ,…mà chúng có điểm chung.

### Chuẩn bị dữ liệu

Chúng tôi sử dụng bộ dữ liệu từ Spotify API truy cập thông tin về bài hát, playlist, và người nghe từ Spotify để tạo dự đoán dựa trên lịch sử và thói quen nghe nhạc của người dùng
Tập dữ liệu đầu vào dùng để phân cụm bao gồm 14675 hàng và 19 cột cùng với tập dữ liệu lịch sử nghe nhạc của người dùng có 85 bài hát.

Tiền xử lí dữ liệu và sử dụng MinMaxScaler để chuẩn hóa dữ liệu.

### Phương pháp thực hiện

Huấn luyện mô hình bằng thuật toán K-Means để phân loại bài hát trong thư viện âm nhạc theo số phân cụm tối ưu nhất
Tiếp đó, Principal Component Analysis (PCA) sẽ được sử dụng để trích xuất các đặc điểm chính của dữ liệu giúp cho gia tăng độ chính xác của thuật toán phân cụm K-means.
Dựa vào dữ liệu nghe của người dùng, từ đó sẽ gợi ý cho người nghe những bài hát mà họ có thể hợp với sở thích nghe của bản thân.

### Kết quả

Qua quá trình điều chỉnh số phân cụm cũng như đối chiếu dữ liệu từ 85 bài hát từ dữ liệu người dùng so với 20 (có thể tùy chỉnh) bài hát mà hệ thống đưa ra, chúng tôi có thể đưa ra được những biểu đồ minh họa cho hiệu suất của mô hình.

Mô hình của của chúng tôi thực hiện khá tốt nhiệm vụ áp dụng K-means để phân cụm nhằm gợi ý bài hát tới người dùng dựa trên danh sách bài hát sẵn có của họ. Mô hình có thể được đưa vào thực tế trong quy mô nhỏ và đơn giản. Tuy nhiên, mô hình cũng vướng phải nhiều sự khó khăn do sự lựa chọn các bài hát thường không chỉ phụ thuộc vào thói quan mà còn dựa vào cảm xúc của người dùng.

Mô hình này của chúng tôi là chỉ là nỗ lực để xem làm cách nào có thể kết hợp một phương pháp đơn giản cho vấn đề gợi ý. Có rất nhiều các phương pháp khác có thể đem lại hiệu suất tốt hơn. Tuy nhiên việc sử dụng K-means đã giảm bớt gánh nặng của việc chọn thuật toán và điều chỉnh tham số.
