# TÓM TẮT TÀI LIỆU DỰ ÁN (Tiếng Việt)

Repo này đi kèm sách *Build a Reasoning Model (From Scratch)* và cung cấp mã nguồn tối thiểu, dễ đọc để học cách tăng cường khả năng reasoning của một LLM nền tảng (Qwen3). Dưới đây là tóm tắt súc tích các nhóm tài liệu.

---
## 1. README_chung & Glossary
- `README_vi.md`: Giới thiệu mục tiêu sách – xây dựng mô hình reasoning nhỏ từ base LLM, triển khai các kỹ thuật: inference-time scaling, self-refinement, reinforcement learning, distillation. Liệt kê chương, bonus, cách trích dẫn.
- `README.md`: Landing page rút gọn, chuyển hướng sang file ngôn ngữ, liệt kê trạng thái chương và hướng dẫn clone repo.
- `GLOSSARY.md`: Bảng thuật ngữ song ngữ chuẩn hóa (LLM, reasoning, inference-time scaling, chain-of-thought, self-consistency...), kèm nguyên tắc dùng và đóng góp.

## 2. Chương Cơ Bản
- Chương 1: Thuần khái niệm về mô hình reasoning; không có mã.
- Chương 2: Sinh văn bản với LLM đã pre-trained. Notebook chính + bài tập. Bonus: hướng dẫn setup Python/GPU, phiên bản LLM tối ưu, torch.compile trên Windows, script chạy inference & chế độ chat (`generate_simple.py`, `chat.py`, `chat_multiturn.py`).
- Chương 3: Đánh giá mô hình reasoning. Notebook chính + script đánh giá MATH-500 (verifier & batched) để kiểm tra độ chính xác và tốc độ.
- Chương 4: Inference-time scaling. Notebook chính + script triển khai CoT prompting và self-consistency sampling trên MATH-500, bảng so sánh độ chính xác/thời gian.
- Các Chương 5–8: TBA (sẽ bổ sung: self-refinement, RL, distillation, cải tiến pipeline).

## 3. Phụ Lục
- Appendix C: Mã nguồn LLM Qwen3 từ-scratch (notebook và module Python) để tham khảo cấu trúc mô hình.
- Appendix F: Các cách phổ biến đánh giá LLM (MMLU, Elo/Bradley–Terry leaderboard, LLM-as-a-judge) kèm mã minh họa.
- Appendix G: Giao diện chat (notebook + mã) cho đa lượt, có bộ nhớ lịch sử.

## 4. Tối Ưu Mô Hình
- `ch02/03_optimized-LLM/README.md`: So sánh `qwen3.py` (cơ bản, dễ đọc) và `qwen3_optimized.py` (dùng `scaled_dot_product` + KV cache tiền cấp phát). Hướng dẫn thay thế import, script `compare_inference.py` để benchmark token/sec, lưu ý trade-off RAM vs tốc độ.

## 5. Inference & Chat Scripts
- `generate_simple.py`: Chạy thử nhanh prompt mặc định hoặc tùy chỉnh, hỗ trợ chọn thiết bị, compile, reasoning variant, KV cache.
- `chat.py`: REPL đơn lượt (không nhớ lịch sử) cho thử nhiều prompt liên tiếp.
- `chat_multiturn.py`: REPL có bộ nhớ; reasoning variant hoạt động tốt hơn base; hỗ trợ lệnh quản lý phiên (`\clear`, `\history`).

## 6. Inference-Time Scaling Scripts (Ch4 Bonus)
- `cot_prompting_math500.py`: Thực hiện chain-of-thought prompting; cải thiện độ chính xác base model đáng kể so với greedy.
- `self_consistency_math500.py` (+ batched): Lấy nhiều mẫu với nhiệt độ/top-p rồi bỏ phiếu/đếm nhất quán; minh họa quan hệ giữa số mẫu, thời gian và độ chính xác.

## 7. Đánh Giá & Leaderboard (Appendix F)
- MMLU: Triển khai các chế độ đánh giá (letter matching, logprob, teacher forcing).
- Leaderboards: Tính Elo, Bradley–Terry để xếp hạng mô hình từ kết quả so cặp hoặc phiếu bầu (`votes.json`).
- LLM-as-a-judge: Script cho phép một LLM đánh giá output của LLM khác – xu hướng mới giảm chi phí human eval.

## 8. Thực Hành & Bài Tập
- Mỗi chương có notebook chính + notebook lời giải bài tập (ví dụ `ch02_exercise-solutions.ipynb`). Bài tập giúp củng cố: sinh văn bản, đánh giá MATH-500, cải thiện reasoning bằng sampling & prompting.

## 9. Phần Cứng & Hiệu Năng
- Thiết kế để chạy được trên phần cứng phổ thông; GPU giúp tăng tốc ở chapter sau. KV cache + torch.compile cải thiện tốc độ (thể hiện trong bảng benchmark).
- Optimized model: nhanh hơn trên GPU với cache + compile; bản cơ bản đôi khi hiệu quả hơn trên CPU ở một số cấu hình.

## 10. Triết Lý Thiết Kế
- Ưu tiên mã ngắn gọn, rõ ràng để học cơ chế nội bộ hơn là tối ưu vi mô phức tạp.
- Các bonus tối ưu (optimized model, batched sampling) tách riêng để không che mờ phần học thuật.

## 11. Đóng Góp & Trích Dẫn
- Không mở rộng code chương chính để giữ đồng bộ với sách in; chấp nhận sửa lỗi dịch, link hỏng.
- Trích dẫn chuẩn: Chicago + BibTeX có trong README.

---
## Tóm Tắt Nhanh Theo Mục Tiêu Học Tập
| Mục tiêu | Tài liệu chính | Bonus hỗ trợ | Kết quả đạt được |
|----------|----------------|--------------|------------------|
| Hiểu khái niệm reasoning | Ch1 README | Glossary | Nắm định nghĩa & bối cảnh |
| Sinh văn bản | Ch2 notebooks | generate_simple.py, chat*.py | Chạy prompt, hiểu pipeline cơ bản |
| Đánh giá mô hình | Ch3 notebooks | MATH-500 scripts | So sánh base vs reasoning |
| Nâng độ chính xác không retrain | Ch4 notebooks | CoT, self-consistency scripts | Cải thiện score qua sampling & prompting |
| Hiểu cấu trúc nội bộ LLM | Appendix C | optimized-LLM README | Phân biệt implement rõ ràng vs tối ưu |
| Đánh giá mở rộng | Appendix F | Leaderboards, judge | Benchmark đa chiều, tự động hóa đánh giá |
| Giao tiếp đa lượt | Appendix G | chat_multiturn.py | Xây session có bộ nhớ |

---
## Gợi Ý Lộ Trình 30–60 Phút
1. Đọc `README_vi.md` phần Mục Lục + Glossary nhanh.
2. Chạy `generate_simple.py` (base vs reasoning prompt mặc định).
3. Mở `compare_inference.py` để benchmark nhanh CPU/GPU.
4. Dùng `cot_prompting_math500.py` với model base để thấy tăng accuracy.
5. Xem bảng self-consistency để hiểu trade-off thời gian.
6. Khám phá `chat_multiturn.py` với reasoning variant.

---
## Liên Kết Nhanh
- Base model code: `reasoning_from_scratch/qwen3.py`
- Optimized model: `reasoning_from_scratch/qwen3_optimized.py`
- Inference helpers: `reasoning_from_scratch/ch02.py`, `ch02/05_use_model/`
- Evaluation scripts: `ch03/02_math500-verifier-scripts/`, `ch04/02_math500-inference-scaling-scripts/`
- Leaderboards & judge: `chF/03_leaderboards/`, `chF/04_llm-judge/`

---
*File này được tạo tự động nhằm cung cấp cái nhìn cô đọng về toàn bộ tài liệu. Có thể cập nhật khi chương TBA bổ sung.*
