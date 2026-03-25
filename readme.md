

## Features

- **Training-Free**: Zero parameter updates, compatible with frozen LLaVA-1.5 and Qwen-VL
- **Hierarchical Correction**: Dynamic layer-wise uncertainty monitoring + local evidence verification
- **Robust Engineering**: Auto-resume from interruptions, OOM recovery, distributed evaluation support
- **Multi-Benchmark**: Supports CHAIR, MME, and LLaVA-Bench-In-the-Wild

## Installation

```bash
pip install -r requirements.txt

Key Dependencies:

    Python ≥ 3.8, CUDA ≥ 11.8
    torch==2.1.2, torchvision==0.16.2
    transformers==4.30.0, accelerate==0.20.3

Project Structure

.
├── ASRF_chair_0129.py      # CHAIR benchmark (caption hallucination)
├── ASRF_mme_0129.py        # MME benchmark (perception)
├── ASRF_llabench_0129.py   # LLaVA-Bench (complex reasoning)
├── requirements.txt        # Dependencies
└── README.md               # This file

Key Features

    Auto-Resume: Automatically skips completed samples based on image_id or question_id
    OOM Protection: Automatic CUDA memory clearing and error recovery
    Distributed: Supports multi-GPU evaluation via torch.distributed

Notes

    Ensure dependent modules are in PYTHONPATH:
        mem_simplified (MemVR implementation)
        my_ed_qa (ED module)
        utils (distributed utilities)
    Update hardcoded paths in scripts to match your environment:
        COCO images path (CHAIR)
        MME benchmark path
        LLaVA-Bench data path
  


