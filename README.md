# Nhận diện ngôn ngữ ký hiệu
Giao tiếp với người khiếm thính là một thử thách khó khăn. Người khiếm thính sử dụng ngôn ngữ ký hiệu để giao tiếp, người bình thường muốn hiểu được người khiếm thính nói gì cần phải đối mặt với việc học ngôn ngữ ký hiệu. Điều này gây cản trở trong giao tiếp. Ngôn ngữ ký hiệu sử dụng cử chỉ tay và biểu cảm khuôn mặt. Trong đó cử chỉ tay để nhận diện các chữ cái và các từ. Sử dụng mô hình mạng khoa học thần kinh học sâu để dự đoán dấu hiệu từ ngữ.

## 1. Mục tiêu:
Để nhận biết được ngôn ngữ ký hiệu sử dụng trí tuệ nhân tạo có các phương pháp dựa trên cảm biến và phương pháp dựa trên Vision:

- Trong công nghệ nhận dạng cử chỉ dựa trên vision, một máy ảnh sẽ ghi lại chuyển động của cơ thể người, đặc biệt là cử chỉ tay để đưa ra ngôn ngữ ký hiệu.

- Trong công nghệ dựa trên cảm biến, các chuyển động của bàn tay và ngón tay trong thời gian thực có thể được theo dõi bằng cách sử dụng cảm biến chuyển động Leap.

Dựa theo công nghệ nhận dạng cử chỉ dựa trên vision, nhóm đã sử dụng *mạng thần kinh tích chập Inception V3* để huấn luyện tạo ra một kiến trúc có thể nhận diện cử chỉ của tay để đưa ra ngôn ngữ.

## 2. Thuật toán:

### 2.1. Tại sao chọn mạng Convolutional Neural Network CNN:
+ CNN rất hiệu quả trong việc giảm số lượng các tham số mà không làm giảm chất lượng của các mô hình. Hình ảnh có kích thước cao (vì mỗi pixel được coi là một tính năng) phù hợp với khả năng được mô tả ở trên của CNN.

+ CNN giữ nguyên dạng hình ảnh không gian 2D.

+ Tất cả các lớp của CNN có nhiều bộ lọc tích hợp hoạt động và quét ma trận tính năng hoàn chỉnh và thực hiện giảm kích thước. Điều này cho phép CNN trở thành một mạng rất phù hợp và phù hợp để phân loại và xử lý hình ảnh.

### 2.2. Tại sao lại cần  Transfer Learning Google Inception Net ?


+ Nhiều lớp đối tượng hơn làm cho sự khác biệt giữa các lớp khó hơn. Ngoài ra, một mạng lưới thần kinh chỉ có thể chứa một lượng thông tin hạn chế, có nghĩa là nếu số lượng lớp trở nên lớn thì có thể không có đủ trọng số để đối phó với tất cả các lớp. Điều này làm giảm độ chính xác của mô hình sau khi thêm nhiều lớp và dữ liệu đào tạo trong bộ dữ liệu.

+ Sự khác biệt chính giữa các Transfer Learning và CNN thông thường là các khối khởi đầu. Chúng liên quan đến việc kết hợp cùng một tenxơ đầu vào với nhiều bộ lọc và kết hợp kết quả của chúng. Ngược lại, CNN thông thường thực hiện một thao tác tích chập duy nhất trên mỗi tenxơ.



