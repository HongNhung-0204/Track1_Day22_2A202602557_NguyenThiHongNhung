# Prompt Log — Lab Day22 (Final Checklist mục 10)

> Chạy ngày 08/10/2026 với Claude (Claude Code) trên số liệu của `NguyenThiHongNhung_Day22_model.xlsx`.
> AI chỉ phản biện; mỗi điểm được ghi accept / partial / reject kèm lý do. Các con số kịch bản do mình tính lại theo công thức trong Excel.

---

## 1. Prompt 4.7.1 — Cost/Job Stress Test

| # | AI nêu | Kiểm tra lại | Quyết định |
|---|---|---|---|
| 1 | Thiếu chi phí: phí thanh toán của kênh bán | Phí Discord Premium Apps 15% = **54% Cost/Job** — lớn hơn token LLM (15%) | **Accept** — đã đưa vào Infra/ván (tab 1, G37:G40) |
| 2 | Thiếu chi phí: LangSmith tracing (`.env.example` bật `LANGCHAIN_TRACING_V2`) | Chưa có số liệu dùng / hóa đơn | **Partial** — chưa đưa vào mô hình; ghi vào việc tháng 1 "lấy hóa đơn thật" |
| 3 | Mẫu số có phải job hoàn thành không? | B66 = (biến đổi + HITL) / B11, B11 = B9 × B10 → đúng là ván hoàn thành | Đã đúng, không sửa |
| 4 | Kiểm tra token | 13 lời gọi/ván, 29.112 token input, ~1.991 token output → LLM $0,0056/ván. Hỏi luật chiếm 87,8% token input vì gửi cả rulebook | **Accept** — thêm việc tháng 2–3: chỉ gửi đoạn luật liên quan |
| 5 | Caching / Batch | Cache prompt hỏi luật tiết kiệm 22,1% chi phí LLM (≈ 3% Cost/Job). Batch không dùng được vì cần realtime | Cache: **Partial** (ghi ở G31:G33, không tính vào mô hình chính cho thận trọng). Batch: **Reject** |
| 6 | Giá có thể đổi | Discord: 15% chỉ áp dụng cho $1M đầu, sau đó 30% → Cost/Job $0,0667, **GM 49,8%**. Railway gấp đôi ($40) → GM 61,5% | **Accept** — ghi rủi ro vào One-Pager |
| 7 | Con số giết mô hình | Tỷ lệ ván hoàn thành sai 2 lần (85,7% → 42,9%) → **GM 34,7%**. Khối lượng < ~760 ván/tháng → GM < 50% | **Accept** — đo tỷ lệ hoàn thành là việc số 1 của tháng 1; thêm bảng theo khối lượng (tab 2, F37:H45) |
| 8 | Số câu hỏi luật/ván có thể cao hơn | 6 câu thay vì 3 → GM 63,8% | Ghi nhận; ảnh hưởng nhỏ, không sửa |

## 2. Prompt 4.7.2 — Value Metric Challenger

| # | AI nêu | Quyết định |
|---|---|---|
| 1 | Model gợi ý Usage (Attribution 6, Autonomy 8). Sao lại chọn Hybrid? | **Reject đổi** — giữ Hybrid vì lý do thị trường: bot Discord và AI quản trò (Friends & Fables, AI Dungeon) đều bán gói tháng. Đã ghi lý do ở tab 3 B31 |
| 2 | Câu hỏi khó: "Ván người chơi bỏ giữa chừng có bị tính không?" | Đã có trong định nghĩa job: **không tính** |
| 3 | Câu hỏi khó: "Server chỉ chơi 5 ván/tháng thì $3,99 ≈ $0,8/ván — đắt" | **Partial** — đưa vào phỏng vấn tháng 1; có thể thêm gói nhỏ hơn sau pilot |
| 4 | Câu hỏi khó: "Đã có bot Ma Sói miễn phí, sao phải trả?" | **Accept** — chưa có bằng chứng sẵn lòng trả; phỏng vấn 5 admin tháng 1 |
| 5 | Hành vi làm lỗ: hỏi luật rất nhiều trong gói | **Accept** — giới hạn số câu hỏi luật trong gói + RAG cắt token (tháng 2–3) |
| 6 | Benchmark AI Dungeon chưa xác minh trực tiếp | **Accept** — ghi rõ "cần kiểm tra tay" ở tab 3 và tab 6 |
