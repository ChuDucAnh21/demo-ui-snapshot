
### Phần : SnapShort - Frontend
#### 🎯 Mục tiêu
- Thiết kế và xây dựng giao diện hệ thống câu hỏi để thu thập thông tin của bé từ phụ huynh (mẹ của bé) qua bộ câu hỏi trong 4 phần chính (Trình độ nền tảng, tư duy và cách tiếp cận, kỹ năng hỗ trợ, sở thích-tâm lý của mẹ )
- Gửi dữ liệu thu thập được đến mô hình AI **AI Backend/API** để nhận lại:
    + 📊 **Biểu đồ tổng quan (Radar Chart)**  của bé về 4 phần câu hỏi
    + 💡 **Lời khuyên phát triển cá nhân hóa** cho bé.
    + 🗺️ **Lộ trình học tập phù hợp** theo độ tuổi, năng lực, hành vi.
#### 📋 Các bước xử lý
1. **Tạo form câu hỏi** (4 phần chính): 
 
-Phần 1: Trình độ nền tảng của bé 
-Phần 2: Thiên hướng tư duy và cách tiếp cận
-Phần 3: Kỹ năng hỗ trợ tổng quát
-Phần 4: Sở thích, tâm lý của mẹ khi dạy con

 (Phần 1 + 3: Trả lời qua các thang điểm: Có = 10 /Thi thoảng = 5/Chưa = 0)
 (Phần 2 + 4: Trả lời bằng các tag tương ứng ở mỗi câu)

2. **Xử lý dữ liệu đầu ra**
- Với phần 1 + 3:
 + Tính điểm trung bình (TB) các câu trong mỗi phần
 + Map sang các trạng thái :
    . **TB >= 8**       --> "Formed" (Đã hình thành)
    . **4 <= TB < 8**  -->  "Emerging" (Đang nảy mầm)
    . **TB < 4**        --> "Seed" (Cần gieo mầm)
- Với phần 2 + 4:
 + Lưu nguyên văn tag trong mỗi câu hỏi (vd : style, challenge, thinking_tendency, theme,...)

3. **Kết nối AI**
   - Gửi dữ liệu đã xử lý tới API AI (hoặc model nội bộ).
   - Nhận phản hồi từ AI gồm: Lời khuyên cho mẹ và lộ trình phát triển cho bé.

4. **Hiển thị kết quả**
   - Trình bày gợi ý AI theo cách trực quan, dễ hiểu ( biểu đồ, lời khuyên, lộ trình học,...).
#### 🛠️ Công nghệ sử dụng
- **Frontend:** React / Next.js + Tailwind CSS
- **Form Handling:** React Hook Form hoặc Formik
- **API Connection:** Fetch API
- **State Management:** useState / useContext / redux-toolkit
- **AI Connection:** gọi API backend

#### 📈 Kết quả kỳ vọng
- Giao diện trực quan, thân thiện.
- Kết quả AI hiển thị rõ ràng, có thể lưu trữ hoặc chỉnh sửa lại câu trả lời.