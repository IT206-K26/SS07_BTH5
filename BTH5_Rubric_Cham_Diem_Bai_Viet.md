# Bài thực hành 5: Xây dựng Rubric để AI chấm điểm bài viết

## 1. Prompt thiết lập vai trò người chấm (System Prompt)

```markdown
# VAI TRÒ (ROLE)
Bạn là một **Giảng viên Đại học chuyên môn về Kỹ năng học thuật và Đánh giá giáo dục**. Nhiệm vụ của bạn là chấm điểm bài viết khoảng 300 từ của sinh viên về chủ đề: *"Vai trò của AI trong hoạt động học tập của sinh viên đại học"* một cách khách quan, nhất quán và có dẫn chứng cụ thể.

# QUY TẮC BẮT BUỘC (CONSTRAINTS)
1. **Không tự ý thay đổi trọng số:** Bắt buộc giữ nguyên thang điểm tối đa của từng tiêu chí (tổng 10 điểm).
2. **Không chấm điểm cảm tính:** Tuyệt đối không đưa ra nhận xét chung chung như "bài viết tốt", "khá ổn" hay "cần cố gắng".
3. **Bắt buộc có minh chứng:** Mọi điểm số ở từng tiêu chí đều phải trích dẫn trực tiếp câu/ý từ bài viết của sinh viên làm bằng chứng.
4. **Không thiên vị độ dài:** Không cộng điểm hay đánh giá cao chỉ vì bài viết dài; chỉ đánh giá chất lượng nội dung, lập luận và sự cô đọng.
5. **Chỉ rõ lỗi và cách sửa:** Với mỗi điểm bị trừ, phải chỉ rõ vị trí lỗi sai và đề xuất câu/hướng chỉnh sửa cụ thể.

# RUBRIC CHẤM ĐIỂM (THANG ĐIỂM 10)
1. **Đúng chủ đề (Tối đa: 2,0 điểm):** Bám sát chủ đề vai trò của AI trong học tập của sinh viên đại học, không lạc đề.
2. **Nội dung và lập luận (Tối đa: 3,0 điểm):** Luận điểm rõ ràng, phân tích sâu sắc, có góc nhìn đa chiều (lợi ích lẫn lưu ý/thách thức), lập luận logic.
3. **Ví dụ minh họa (Tối đa: 2,0 điểm):** Có ví dụ thực tế, cụ thể gắn với đời sống học tập đại học (công cụ, tình huống cụ thể), hỗ trợ làm rõ luận điểm.
4. **Cấu trúc bài viết (Tối đa: 1,5 điểm):** Có bố cục Mở đoạn – Thân đoạn – Kết đoạn mạch lạc, có từ nối liên kết giữa các ý.
5. **Ngữ pháp và diễn đạt (Tối đa: 1,5 điểm):** Đúng chính tả, ngữ pháp tiếng Việt, dùng từ chuẩn xác, tránh lặp từ và văn nói.

# QUY TRÌNH THỰC HIỆN (WORKFLOW)
Khi nhận được bài viết của sinh viên, hãy thực hiện lần lượt:
1. Đọc kỹ toàn bộ bài viết.
2. Đánh giá và cho điểm từng tiêu chí dựa trên Rubric (trích dẫn minh chứng cụ thể).
3. Tổng hợp **Bảng đối chiếu giữa Tiêu chí – Điểm số – Minh chứng**.
4. Phân tích **Điểm mạnh** và **Điểm yếu** của bài viết.
5. Đưa ra **Đề xuất cải thiện chi tiết** (chỉ rõ lỗi và viết lại câu mẫu).
6. Tính **Tổng điểm chính xác trên thang 10**.

# BÀI VIẾT CỦA SINH VIÊN
[Dán bài viết của sinh viên vào đây]
```

---

## 2. Rubric chấm điểm chi tiết (Dạng bảng)

| Tiêu chí | Điểm tối đa | Mức Xuất sắc (90% – 100%) | Mức Khá (70% – 89%) | Mức Trung bình (50% – 69%) | Mức Yếu (< 50%) |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **1. Đúng chủ đề** | **2,0** | Tập trung hoàn toàn vào vai trò của AI trong học tập đại học, không lan man. | Bám sát chủ đề nhưng có 1–2 ý hơi rộng ngoài phạm vi sinh viên. | Đề cập đến AI nhưng nói chung chung về đời sống, ít gắn với học tập. | Lạc đề hoàn toàn hoặc chỉ định nghĩa AI. |
| **2. Nội dung và lập luận** | **3,0** | Luận điểm sắc bén, phân tích đa chiều (lợi ích & rủi ro), lập luận chặt chẽ. | Có 2–3 luận điểm rõ ràng nhưng phân tích chưa sâu hoặc thiếu góc nhìn phản biện. | Ý tưởng rời rạc, mang tính liệt kê, thiếu giải thích logic. | Nội dung sơ sài, sáo rỗng, lặp ý. |
| **3. Ví dụ minh họa** | **2,0** | Có ít nhất 2 ví dụ thực tế, cụ thể, gắn trực tiếp với việc học đại học. | Có ví dụ nhưng còn hơi chung chung, chưa phân tích rõ tác dụng. | Chỉ nhắc tên công cụ AI mà không có ngữ cảnh ứng dụng cụ thể. | Không có ví dụ minh họa. |
| **4. Cấu trúc bài viết** | **1,5** | Bố cục Mở – Thân – Kết rõ ràng, câu chủ đề tốt, chuyển ý mượt mà. | Đủ 3 phần nhưng chuyển ý giữa các câu còn hơi đột ngột. | Thiếu câu mở đoạn hoặc kết đoạn; các ý sắp xếp lộn xộn. | Không có cấu trúc đoạn văn rõ ràng. |
| **5. Ngữ pháp và diễn đạt** | **1,5** | Không lỗi chính tả/ngữ pháp, văn phong học thuật, cô đọng, không lặp từ. | Có 1–2 lỗi diễn đạt nhỏ hoặc lặp từ nhẹ, không ảnh hưởng ý nghĩa. | Có 3–4 lỗi ngữ pháp, dùng văn nói hoặc câu quá dài rườm rà. | Nhiều lỗi chính tả, câu tối nghĩa, khó hiểu. |
| **TỔNG ĐIỂM** | **10,0** | | | | |

---

## 3. Bài viết mẫu của sinh viên (~300 từ)

> Trong bối cảnh chuyển đổi số hiện nay, trí tuệ nhân tạo (AI) đang đóng vai trò ngày càng quan trọng trong hoạt động học tập của sinh viên đại học. Trước hết, AI giúp sinh viên tiết kiệm rất nhiều thời gian trong việc tìm kiếm và tổng hợp kiến thức. Thay vì phải đọc hàng trăm trang tài liệu dày cộm, sinh viên có thể sử dụng các công cụ như ChatGPT hay Gemini để tóm tắt nội dung chính, giải thích các khái niệm khó hiểu theo cách đơn giản hơn. Thứ hai, AI đóng vai trò như một gia sư cá nhân hoạt động 24/7. Sinh viên có thể dùng AI để luyện tập ngoại ngữ, kiểm tra lỗi ngữ pháp tiếng Anh hoặc nhờ gợi ý cách sửa lỗi code khi học lập trình. Ví dụ, một sinh viên ngành công nghệ thông tin có thể nhờ AI giải thích nguyên nhân lỗi trong đoạn mã Python và học cách tối ưu thuật toán ngay tại nhà. Tuy nhiên, bên cạnh những lợi ích to lớn thì AI cũng mang lại nhiều thách thức không nhỏ nếu sinh viên sử dụng không đúng cách. Việc lạm dụng AI để làm bài tập hộ hay viết tiểu luận từ đầu đến cuối sẽ làm giảm khả năng tư duy độc lập và khiến sinh viên dễ vi phạm đạo văn. Ngoài ra, thông tin do AI tạo ra đôi khi vẫn chưa chính xác hoàn toàn nên người học cần biết cách kiểm chứng lại. Tóm lại, AI là một công cụ hỗ trợ học tập vô cùng hữu ích cho sinh viên đại học, nhưng bản thân mỗi sinh viên cần sử dụng AI một cách thông minh và có trách nhiệm để AI thực sự giúp ích cho mình chứ không phải phụ thuộc vào nó.

*(Độ dài: ~300 từ)*

---

## 4. Kết quả AI chấm điểm & Bảng đối chiếu Tiêu chí – Điểm số – Minh chứng

| Tiêu chí | Điểm tối đa | Điểm đạt được | Minh chứng trực tiếp từ bài viết & Lý do chấm điểm |
| :--- | :---: | :---: | :--- |
| **1. Đúng chủ đề** | 2,0 | **2,0** | Toàn bộ đoạn văn tập trung phân tích vai trò của AI trong việc học của sinh viên đại học. Câu mở đoạn khẳng định rõ: *"trí tuệ nhân tạo (AI) đang đóng vai trò ngày càng quan trọng trong hoạt động học tập của sinh viên đại học."* |
| **2. Nội dung và lập luận** | 3,0 | **2,5** | **Đạt:** Có 2 luận điểm chính rõ ràng (tiết kiệm thời gian tổng hợp kiến thức; đóng vai trò gia sư 24/7) và có góc nhìn phản biện về rủi ro (*"lạm dụng AI... làm giảm khả năng tư duy độc lập"*, *"thông tin... chưa chính xác hoàn toàn"*). **Trừ 0,5đ:** Phần phân tích rủi ro mới dừng ở mức liệt kê ngắn gọn, chưa làm rõ giải pháp cụ thể để sinh viên kiểm chứng thông tin hay sử dụng AI có trách nhiệm. |
| **3. Ví dụ minh họa** | 2,0 | **1,5** | **Đạt:** Có nêu tên công cụ cụ thể (*"ChatGPT hay Gemini"*) và một tình huống rõ ràng (*"một sinh viên ngành công nghệ thông tin có thể nhờ AI giải thích nguyên nhân lỗi trong đoạn mã Python"*). **Trừ 0,5đ:** Ví dụ cho mảng rủi ro/lạm dụng chưa có dẫn chứng cụ thể; ví dụ luyện ngoại ngữ chỉ nêu chung chung, chưa gắn với tình huống học tập cụ thể. |
| **4. Cấu trúc bài viết** | 1,5 | **1,5** | Đủ 3 phần mạch lạc: Mở đoạn (câu 1), Thân đoạn (triển khai ý bằng từ nối *"Trước hết"*, *"Thứ hai"*, *"Tuy nhiên"*, *"Ngoài ra"*), Kết đoạn (bắt đầu bằng *"Tóm lại"*). |
| **5. Ngữ pháp và diễn đạt** | 1,5 | **1,0** | **Đạt:** Không sai chính tả, câu văn rõ nghĩa. **Trừ 0,5đ:** Còn dùng văn nói (*"rất nhiều"*, *"dày cộm"*, *"giúp ích cho mình"*) và lặp từ *"AI"* quá dày (11 lần trong 1 đoạn), câu kết hơi dài và lặp ý. |
| **TỔNG ĐIỂM** | **10,0** | **8,5 / 10** | **Bài viết đạt mức Khá – Giỏi, bám sát chủ đề và có tư duy đa chiều.** |

---

## 5. Nhận xét chi tiết và Đề xuất cải thiện

### Điểm mạnh
* **Bám sát yêu cầu đề bài:** Giữ đúng dung lượng khoảng 300 từ, đi thẳng vào trọng tâm vấn đề ngay từ câu đầu tiên.
* **Tư duy cân bằng (hai chiều):** Không chỉ khen ngợi lợi ích của AI mà còn đề cập đến mặt trái như giảm tư duy độc lập, đạo văn và độ chính xác của dữ liệu.
* **Mạch lạc:** Sử dụng hiệu quả các từ nối chuyển ý (*Trước hết, Thứ hai, Tuy nhiên, Ngoài ra, Tóm lại*), giúp người đọc dễ theo dõi lập luận.

### Điểm yếu (Lỗi cần khắc phục)
1. **Lỗi văn phong chưa mang tính học thuật:** Một số cụm từ còn mang sắc thái khẩu ngữ như *"tài liệu dày cộm"*, *"tiết kiệm rất nhiều thời gian"*, *"giúp ích cho mình"*.
2. **Lỗi lặp từ:** Từ *"AI"* và *"sinh viên"* xuất hiện liên tục trong nhiều câu liền kề, làm giảm độ mượt mà của đoạn văn.
3. **Câu kết đoạn còn dài và chưa cô đọng:** Câu cuối dài hơn 45 từ, vế sau lặp lại ý *"phụ thuộc"* đã nói ở thân đoạn.

### Đề xuất cách sửa cụ thể
* **Sửa lỗi văn phong học thuật:**
  * *Câu gốc:* "Thay vì phải đọc hàng trăm trang tài liệu dày cộm..."
  * *Đề xuất sửa:* "Thay vì phải xử lý khối lượng tài liệu đồ sộ..."
* **Sửa lỗi lặp từ:**
  * Thay thế linh hoạt từ *"AI"* bằng *"công nghệ này"*, *"các mô hình trí tuệ nhân tạo"*, *"công cụ thông minh"*; thay *"sinh viên"* bằng *"người học"*.
* **Viết lại câu kết đoạn cho súc tích:**
  * *Câu gốc:* "Tóm lại, AI là một công cụ hỗ trợ học tập vô cùng hữu ích cho sinh viên đại học, nhưng bản thân mỗi sinh viên cần sử dụng AI một cách thông minh và có trách nhiệm để AI thực sự giúp ích cho mình chứ không phải phụ thuộc vào nó."
  * *Đề xuất sửa:* "Tóm lại, trí tuệ nhân tạo là trợ thủ đắc lực giúp nâng cao hiệu suất học tập ở bậc đại học, nhưng hiệu quả thực sự chỉ đạt được khi người học biết ứng dụng công nghệ này một cách chủ động, có kiểm chứng và giữ vững tư duy độc lập."
