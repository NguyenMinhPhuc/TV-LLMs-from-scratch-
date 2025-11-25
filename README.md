<!-- Bilingual landing page -->
# Build A Reasoning Model (From Scratch)

**Language / Ngôn ngữ:** [English](README_en.md) | [Tiếng Việt](README_vi.md)

**Glossary / Thuật ngữ:** See [`GLOSSARY.md`](GLOSSARY.md) for standardized bilingual terminology (LLM, reasoning, inference-time scaling, distillation, etc.).

Welcome! This repository accompanies the book *Build a Reasoning Model (From Scratch)*. To keep the code stable while offering multilingual docs, the full book README now lives in separate language files:

- English full README: `README_en.md`
- Vietnamese translation: `README_vi.md`

## Quick Links

- Source code repository (GitHub): https://github.com/rasbt/reasoning-from-scratch
- Book (Manning): https://mng.bz/lZ5B
- ISBN: 9781633434677
- Glossary: [`GLOSSARY.md`](GLOSSARY.md)

## Getting Started

Clone (shallow) the repository:
```bash
git clone --depth 1 https://github.com/rasbt/reasoning-from-scratch.git
```

Then pick your preferred language:
- Open `README_en.md` for the original English.
- Open `README_vi.md` for the Vietnamese translation (technical terms kept in English where appropriate).

## Chapter Index (Snapshot)

| Chapter                                  | Status           | Main Code                               |
| ---------------------------------------- | ---------------- | --------------------------------------- |
| 1 Understanding Reasoning Models         | Conceptual       | (see notebook index in language README) |
| 2 Generating Text with a Pre-trained LLM | Code + Exercises | ch02/01_main-chapter-code               |
| 3 Evaluating Reasoning Models            | Code + Exercises | ch03/01_main-chapter-code               |
| 4 Inference-Time Scaling                 | Code + Exercises | ch04/01_main-chapter-code               |
| 5 Self-Refinement (Inference-Time)       | TBA              | —                                       |
| 6 Reinforcement Learning                 | TBA              | —                                       |
| 7 Distillation for Efficient Reasoning   | TBA              | —                                       |
| 8 Pipeline Improvements & Future         | TBA              | —                                       |
| Appendix C Qwen3 Source                  | Code             | chC/01_main-chapter-code                |
| Appendix F Evaluation Approaches         | Code             | chF/01_main-chapter-code                |

## Tests (CI Badges)

[![Linux](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-linux.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-linux.yml)
[![macOS](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-macos.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-macos.yml)
[![Windows](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-windows.yml/badge.svg)](https://github.com/rasbt/reasoning-from-scratch/actions/workflows/tests-windows.yml)

## How to Navigate

For detailed explanations, hardware notes, exercises, and bonus material, open the language-specific README.

## Contributing

To preserve consistency with the print book, feature additions to core chapter code are not accepted. Issues about translation typos or broken links are welcome.

## Citation (English)

Raschka, Sebastian. *Build A Reasoning Model (From Scratch)*. Manning, 2025. ISBN: 9781633434677.

BibTeX:
```bibtex
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

---
For full content choose a language file above. This landing page stays minimal to reduce duplication.
