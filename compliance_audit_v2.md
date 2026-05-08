**Tên startup:** MindMesh - AI Research Assistant
**Ngày rà soát:** 08/05/2026

---

# 1. Đối chiếu AI Audit vs Workshop 1–2–3

| Loại vi phạm | Workshop liên quan | Đối chiếu |
| --- | --- | --- |
| Marketing thổi phồng (Kera) | WS1 — Claim audit | AI audit phát hiện thêm rủi ro ở claim “summary đủ để ra quyết định” và “giảm hallucination”, trong khi WS1 ban đầu chủ yếu tập trung vào claim tốc độ và productivity |
| Tầng rủi ro AI | WS2 — Territorial scope | WS2 đã classify “Trung bình”, AI audit xác nhận cùng tầng nhưng bổ sung lập luận rằng sản phẩm thuộc educational assistance + GenAI nên không thể classify “thấp” |
| Vendor / payment risk | WS3 — Document trail | WS3 chưa có hồ sơ vendor review, chưa có DPA/SLA/audit trail cho DeepSeek/OpenAI; AI audit đánh dấu đây là pattern gần với failure kiểu Pips |
| Dữ liệu cá nhân | WS2 + Tech stack | WS2 có nhắc cross-border transfer nhưng AI audit phát hiện thêm thiếu CTIA, DPIA, retention policy, consent flow và data processing disclosure |
| Grounded AI claim | WS1 + PRD | Claim “source-grounded” và “giảm hallucination” chưa có benchmark factual accuracy hoặc hallucination evaluation |
| Academic decision support | PRD | AI audit phát hiện wording “đủ để ra quyết định” có thể bị hiểu là AI đủ tin cậy để thay thế academic judgement |
| Query logging / behavior tracking | WS2 | WS2 có liệt kê behavioral data nhưng chưa phân tích rằng query history + accept/reject workflow có thể trở thành dữ liệu cá nhân hành vi học thuật |

---
# 2. Danh sách vi phạm tổng hợp
## VI PHẠM 1 — Claim “summary đủ để ra quyết định”

* Luật áp dụng:
  * BLHS Điều 198
  * Luật AI VN Điều 9
* Bằng chứng:
> “Tạo tóm tắt ‘đủ để ra quyết định’ cho từng bài”
* Pattern:
  * Kera 11/2025 — claim vượt quá năng lực thật
* Rủi ro:
  * User có thể hiểu AI đủ chính xác để thay thế việc đọc paper thật.
* Workshop liên quan:
  * WS1 bỏ sót mức độ pháp lý của wording này.
* Mức độ:
  * Cao

### 3 hành động sửa
1. Đổi wording thành:
   > “summary hỗ trợ quyết định paper nào nên đọc sâu hơn”
2. Thêm disclaimer:
   > “AI summary không thay thế việc đọc paper gốc”
3. Build benchmark accuracy nội bộ trên 20–30 paper mẫu

---
## VI PHẠM 2 — Claim giảm thời gian đọc paper

* Luật áp dụng:
  * BLHS Điều 198
* Bằng chứng:
> “User có thể tìm được ít nhất 1–2 paper hữu ích trong <5 phút”
* Pattern:
  * Kera — dùng số liệu chưa chứng minh để marketing
* Rủi ro:
  * Đây là quantified productivity claim nhưng chưa có user study thật.
* Workshop liên quan:
  * WS1 có detect nhưng chưa coi là priority pháp lý cao.
* Mức độ:
  * Cao

### 3 hành động sửa
1. Gỡ số “<5 phút” khỏi landing page public
2. Nếu giữ metric → ghi rõ sample size + điều kiện test
3. Tách “goal metric” khỏi “marketing promise”

---
## VI PHẠM 3 — Claim “giảm hallucination và tăng độ tin cậy”

* Luật áp dụng:
  * BLHS Điều 198
  * Luật AI VN Điều 9
* Bằng chứng:
> “retrieval và ranking kết hợp heuristic để giảm hallucination và tăng độ tin cậy”
* Pattern:
  * Kera — deterministic wording cho hệ thống probabilistic
* Rủi ro:
  * Chưa có benchmark factuality.
* Mức độ:
  * Trung bình-cao

### 3 hành động sửa
1. Đổi wording thành:
   > “hạn chế hallucination bằng citation + retrieval”
2. Build hallucination log
3. Add “confidence / uncertainty notice” vào UI

---

## VI PHẠM 4 — Chuyển dữ liệu người dùng ra nước ngoài nhưng chưa có CTIA

* Luật áp dụng:
  * PDPL Điều 30
* Bằng chứng:
> “Primary model: DeepSeek”
> “LLM API cho summarization”
* Pattern:
  * CIC leak 9/2025
* Rủi ro:
  * Query học thuật có thể chứa dữ liệu cá nhân hoặc unpublished research.
* Workshop liên quan:
  * WS2 có detect cross-border nhưng chưa nêu CTIA.
* Mức độ:
  * Cao

### 3 hành động sửa

1. Viết CTIA draft nội bộ
2. Thêm consent flow trước query/upload
3. Viết privacy policy mô tả vendor + retention

---
## VI PHẠM 5 — Không có DPIA cho behavioral learning data

* Luật áp dụng:
  * PDPL Điều 30
* Bằng chứng:
> “Ghi nhận feedback để cải thiện ranking”
* Pattern:
  * CIC — collect behavioral data nhưng thiếu auditability
* Rủi ro:
  * Query history + accept/reject = behavioral academic profile.
* Mức độ:
  * Cao

### 3 hành động sửa
1. Viết DPIA 2–3 trang
2. Định nghĩa retention period
3. Add delete/export data flow cho user

---
## VI PHẠM 6 — Sai / thiếu phân loại tầng rủi ro AI
* Luật áp dụng:
  * Luật AI VN Điều 9
* Bằng chứng:
> “hỗ trợ literature review”
> “summary đủ để ra quyết định”
* Pattern:
  * Startup EdTech classify thấp để né compliance
* Rủi ro:
  * Có tác động trực tiếp tới workflow học thuật.
* Workshop liên quan:
  * WS2 classify đúng “trung bình” nhưng chưa có compliance action.
* Mức độ:
  * Trung bình

### 3 hành động sửa

1. Internal memo classify “Medium-risk AI assistant”
2. Add AI disclosure banner
3. Add human verification requirement

---
## VI PHẠM 7 — Không có hồ sơ vendor review / DPA / SLA
* Luật áp dụng:
  * PDPL Điều 30
* Bằng chứng:
> “Primary: DeepSeek”
> “ưu tiên chi phí thấp”
* Pattern:
  * Pips — founder không chứng minh được đã thẩm định vendor
* Rủi ro:
  * Vendor có thể retain prompt hoặc train model bằng user data.
* Workshop liên quan:
  * WS3 detect thiếu vendor review nhưng chưa ưu tiên cao.
* Mức độ:
  * Trung bình-cao

### 3 hành động sửa

1. Build vendor review checklist
2. Document data retention policy của vendor
3. Chuẩn bị fallback vendor/local model

---
# 3. TOP 5 nghiêm trọng nhất

| Rank | Vi phạm                              | Lý do                                   |
| ---- | ------------------------------------ | --------------------------------------- |
| 1    | Cross-border transfer không có CTIA  | Dính trực tiếp PDPL Điều 30             |
| 2    | Claim “summary đủ để ra quyết định”  | Dễ bị xem là misleading AI capability   |
| 3    | Không có DPIA                        | Thiếu hồ sơ compliance nền tảng         |
| 4    | Claim productivity chưa có benchmark | Dễ thành evidence marketing misleading  |
| 5    | Vendor không có review / DPA         | Không chứng minh được founder diligence |

