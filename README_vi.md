# Xây Dựng Một Mô Hình Reasoning (Từ Con Số 0)

**Ngôn ngữ / Language:** [Tiếng Việt](README_vi.md) | [English](README_en.md)

(*Đây là bản dịch tiếng Việt của README gốc; các thuật ngữ kỹ thuật như LLM, reasoning, inference-time scaling, reinforcement learning, distillation được giữ nguyên để chính xác.*)

> Glossary / Thuật ngữ chuẩn: xem [`GLOSSARY.md`](GLOSSARY.md) để dùng thống nhất các thuật ngữ (LLM, reasoning, inference-time scaling, distillation, v.v.).

Kho lưu trữ (repository) này chứa mã nguồn để phát triển một mô hình LLM reasoning và là kho mã chính thức đi kèm với cuốn sách [*Build a Reasoning Model (From Scratch)*](https://mng.bz/lZ5B).

<br>
<br>

<a href="https://mng.bz/lZ5B"><img src="https://sebastianraschka.com/images/reasoning-from-scratch-images/cover.webp?123" width="250px"></a>

(Ấn màu toàn bộ.)

<br>

Trong [*Build a Reasoning Model (From Scratch)*](https://mng.bz/lZ5B), bạn sẽ học và hiểu cách một reasoning large language model (LLM) hoạt động.

"Reasoning" (khả năng lập luận) là một trong những hướng phát triển gần đây vừa thú vị vừa quan trọng để cải thiện LLMs, nhưng cũng rất dễ gây hiểu nhầm nếu bạn chỉ nghe chữ reasoning và đọc lý thuyết. Vì vậy cuốn sách này chọn cách tiếp cận thực hành. Chúng ta sẽ bắt đầu với một base LLM đã pre-trained và tự tay bổ sung các khả năng reasoning từng bước bằng mã, để bạn thấy rõ cơ chế bên trong.

Các phương pháp trong sách hướng dẫn bạn xây dựng một mô hình reasoning nhỏ nhưng đầy đủ chức năng phục vụ mục đích học tập. Nó phản chiếu các cách tiếp cận dùng để tạo ra những mô hình reasoning quy mô lớn như DeepSeek R1, GPT-5 Thinking và những mô hình khác. Ngoài ra, sách còn có mã tải trọng số (weights) của các mô hình đã được pretrained.

- Liên kết kho [source code chính thức](https://github.com/rasbt/reasoning-from-scratch)
- Liên kết sách tại [Manning](https://mng.bz/lZ5B) (website nhà xuất bản)
- Liên kết trang sách trên Amazon.com (TBD)
- ISBN 9781633434677

<br>
<br>

Để tải bản sao repository này, bấm nút [Download ZIP](https://github.com/rasbt/reasoning-from-scratch/archive/refs/heads/main.zip) hoặc chạy lệnh sau trong terminal:

```bash
git clone --depth 1 https://github.com/rasbt/reasoning-from-scratch.git
```

<br>

> **Mẹo:**
> Chapter 2 cung cấp thêm mẹo cài đặt Python, quản lý gói và thiết lập môi trường coding.

<br>
<br>

## Mục Lục (Đang cập nhật)

[![Code tests Linux](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-linux.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-linux.yml)
[![Code tests macOS](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-macos.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-macos.yml)
[![Code tests Windows](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-windows.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-windows.yml)

| Chapter Title                                                 | Main Code                                                                                                                                                     |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ch 1: Hiểu các mô hình Reasoning                              | Không có code                                                                                                                                                 |
| Ch 2: Sinh văn bản với một LLM đã Pre-trained                 | - [ch02_main.ipynb](ch02/01_main-chapter-code/ch02_main.ipynb)<br/>- [ch02_exercise-solutions.ipynb](ch02/01_main-chapter-code/ch02_exercise-solutions.ipynb) |
| Ch 3: Đánh giá các mô hình Reasoning                          | - [ch03_main.ipynb](ch03/01_main-chapter-code/ch03_main.ipynb)<br/>- [ch03_exercise-solutions.ipynb](ch03/01_main-chapter-code/ch03_exercise-solutions.ipynb) |
| Ch 4: Cải thiện Reasoning bằng Inference-Time Scaling         | - [ch04_main.ipynb](ch04/01_main-chapter-code/ch04_main.ipynb)<br/>- [ch04_exercise-solutions.ipynb](ch04/01_main-chapter-code/ch04_exercise-solutions.ipynb) |
| Ch 5: Inference-Time Scaling thông qua Self-Refinement        | TBA                                                                                                                                                           |
| Ch 6: Huấn luyện mô hình Reasoning với Reinforcement Learning | TBA                                                                                                                                                           |
| Ch 7: Distilling mô hình Reasoning để Reasoning hiệu quả      | TBA                                                                                                                                                           |
| Ch 8: Cải thiện pipeline Reasoning và hướng tương lai         | TBA                                                                                                                                                           |
| Appendix A: Tài liệu tham khảo và đọc thêm                    | Không có code                                                                                                                                                 |
| Appendix B: Lời giải bài tập                                  | Code và lời giải nằm trong subfolder của từng chapter                                                                                                         |
| Appendix C: Mã nguồn LLM Qwen3                                | - [chC_main.ipynb](chC/01_main-chapter-code/chC_main.ipynb)                                                                                                   |
| Appendix D                                                    | TBA                                                                                                                                                           |
| Appendix E                                                    | TBA                                                                                                                                                           |
| Appendix F: Các cách phổ biến đánh giá LLM                    | - [chF_main.ipynb](chF/01_main-chapter-code/chF_main.ipynb)                                                                                                   |

<br>
&nbsp;

Sơ đồ tư duy dưới đây tóm tắt các kỹ thuật chính được đề cập trong sách.

<img src="https://sebastianraschka.com/images/reasoning-from-scratch-images/mental-model.webp" width="650px">

<br>

&nbsp;
## Sách Đi Kèm (Companion Book)

Lưu ý *Build A Reasoning Model (From Scratch)* là một cuốn sách độc lập tập trung vào các phương pháp cải thiện khả năng reasoning của LLM.

Trong sách này, ta làm việc với một base LLM open-source đã pre-trained (Qwen3) và tự code áp dụng các phương pháp reasoning từ đầu. Bao gồm inference-time scaling, reinforcement learning và distillation.

Tuy nhiên, nếu bạn quan tâm cách một base LLM "thông thường" được hiện thực, bạn có thể thích cuốn trước của tác giả, [*Build a Large Language Model (From Scratch)*](https://amzn.to/4fqvn0D).

<a href="https://amzn.to/4fqvn0D"><img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/cover.jpg?123" width="120px"></a>

- [Amazon link](https://amzn.to/4fqvn0D)
- [Manning link](http://mng.bz/orYv)
- [GitHub repository](https://github.com/rasbt/LLMs-from-scratch)

<br>
&nbsp;

## Yêu Cầu Phần Cứng

Code trong các chapter chính được thiết kế để chạy chủ yếu trên phần cứng tiêu dùng (consumer hardware) trong thời gian hợp lý và không đòi hỏi server chuyên dụng. Cách tiếp cận này giúp nhiều đối tượng có thể thực hành. Thêm nữa, code tự động dùng GPU nếu có. Nói ngắn gọn: các chapter 2-4 chạy tốt trên cả CPU và GPU. Với chapter 5 và 6, khuyến nghị dùng GPU nếu bạn muốn tái tạo kết quả.

(Xem thêm tài liệu [setup_tips](ch02/https://github.com/rasbt/reasoning-from-scratch/blob/main/ch02/01_main-chapter-code/python-instructions.md) để biết khuyến nghị bổ sung.)

&nbsp;
## Bài Tập

Mỗi chapter có nhiều bài tập. Lời giải tóm tắt ở Appendix B; notebook mã tương ứng nằm trong thư mục chapter chính (ví dụ [`ch02/01_main-chapter-code/ch02_exercise-solutions.ipynb`](ch02/01_main-chapter-code/ch02_exercise-solutions.ipynb)).

&nbsp;
## Tài Liệu Bonus

Một số thư mục chứa nội dung tùy chọn dành cho bạn đọc quan tâm:

- **Chapter 2: Generating Text with a Pre-trained LLM**
  - [Tùy chọn cài đặt Python & khuyến nghị Cloud GPU](ch02/02_setup-tips)
  - [Dùng phiên bản LLM tối ưu GPU](ch02/03_optimized-LLM)
  - [Dùng `torch.compile()` trên Windows](ch02/04_torch-compile-windows)
  - [Chạy inference và chat với model](ch02/05_use_model)
- **Chapter 3: Evaluating LLMs**
  - [MATH-500 Verifier Scripts](ch03/02_math500-verifier-scripts)

- **Chapter 4: Improving Reasoning with Inference-Time Scaling**
  - [Inference Scaling trên MATH-500](ch04/02_math500-inference-scaling-scripts)

- **Appendix F: Common Approaches to LLM Evaluation**
  - [Phương pháp đánh giá MMLU](chF/02_mmlu)
  - [LLM leaderboards](chF/03_leaderboards)
  - [LLM-as-a-judge](chF/04_llm-judge)

&nbsp;
## Hỏi Đáp, Phản Hồi, Đóng Góp

Tôi hoan nghênh mọi phản hồi, tốt nhất chia sẻ qua [Manning Discussion Forum](https://livebook.manning.com/forum?product=raschka2&page=1) hoặc [GitHub Discussions](https://github.com/rasbt/reasoning-from-scratch/discussions). Tương tự, nếu bạn có câu hỏi hoặc muốn trao đổi ý tưởng, cứ đăng lên các kênh trên.

Lưu ý: vì repository này chứa code tương ứng với một cuốn sách in, hiện tại tôi không thể nhận các đóng góp mở rộng nội dung code chính của chapter, vì sẽ tạo chênh lệch so với sách giấy. Giữ đồng nhất giúp trải nghiệm mượt mà cho mọi người.

&nbsp;
## Trích Dẫn (Citation)

Nếu bạn thấy cuốn sách hoặc code hữu ích cho nghiên cứu, hãy cân nhắc trích dẫn.

Chicago-style:

> Raschka, Sebastian. *Build A Reasoning Model (From Scratch)*. Manning, 2025. ISBN: 9781633434677.

BibTeX:

```
@book{build-llms-from-scratch-book,
  author       = {Sebastian Raschka},
  title        = {Build A Reasoning Model (From Scratch)},
  publisher    = {Manning},
  year         = {2025},
  isbn         = {9781633434677},
  url          = {https://mng.bz/lZ5B},
  github       = {https://github.com/rasbt/reasoning-from-scratch}
}
```
