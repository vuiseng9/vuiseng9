**Distributed & Parallel**
* [Megatron, Transformed!][mtuts] *A Hands-on Tutorial on Replicating Empirical Trends in Distributed Training and Model Parallelism. 60+ runs across DP → ZeRO → TP → SP → CP → PP → VPP → EP.* 
* MLPerf Training Rundowns: [v5.1 (Nov'25)][mlperf-t5.1-rd]  on *Llama 3.1-8B, Flux.1*, and [v6.0 (June'26)][mlperf-t6.0-rd] on newly-added MoE *DeepSeek-V3, GPT-OSS*.
* [*(In Progress)*][ep-comm] GPU-Initiated EP Comm: MoE dispatch/combine with PyTorch Symmetric Memory. 

**Narrow Precision Training**
* [Quantized Training in FP4(8)][qt]: *Concepts and Pytorch Implementation using cuBLASLt and Microxcaling.*
* PoC [nvfp4 forward + mxfp8 backward recipe][nv4f_mx8b_pr] in *Transformer Engine*, *[faster][faster-qat]* than nvfp4-QAT.

**Modeling Front**
* [moe-lab][moelab]: *Rigorous MoE design ablations you can run at home. Notably, DeepSeek-V3 Router load-biasing turns out to be [surprisingly effective][moelab-gif]. Implemented autograd for `F.grouped_mm`, >20% [speedup][moelab-groupmm] on average.*
  
**Model Optimization for Efficient Inference**
* Post-Training Statistical Calibration for Higher Activation Sparsity,
    <small><i>[[ENLSP 2024 Spotlight 7](https://neurips2024-enlsp.github.io/), 
    [Paper](https://arxiv.org/abs/2412.07174),
    [Oral](https://neurips.cc/virtual/2024/106426),
    [Code](https://github.com/IntelLabs/SCAP),
    [Integrated](https://github.com/openvinotoolkit/nncf/blob/develop/src/nncf/experimental/torch/sparsify_activations/ActivationSparsity.md)]  </i></small>

* *Pre-LLM explosion* — [Unified HuggingFace Trainer][mlperf-i-v3-jpqd] for Joint [Pruning][nncf-mvmt], Quantization, and Distillation ([JPQD][nncf-jpqd-pr]), integrating OpenVINO NNCF and runtime. 16× more BERT serving throughput on Xeon Sapphire Rapids. See [MLPerf][jpqd-bench] Inference 3.0 submission. [Applicable][jpqd-examples] to vision, audio models.

*Perhaps useful: [dlbp][dlbp], [dockerhub][dhub], [HuggingFace][hf]*


[scap-arvix]: https://arxiv.org/abs/2412.07174
[qt]: https://github.com/vuiseng9/fp4-training
[mtuts]: https://github.com/vuiseng9/megatron-tutorials 
[nvfp4-bench]: https://github.com/vuiseng9/nemo-perf-nvfp4
[mlperf-i-v3-jpqd]: https://github.com/mlcommons/inference_results_v3.0/tree/main/open/Intel/code/bert-99.9_jpqd-large/openvino-cpu#intels-jpqd-bert-mlperf-v30-submission
[jpqd-bench]: https://github.com/mlcommons/inference_results_v3.0/tree/main/open/Intel/code/bert-99.9_jpqd-large/openvino-cpu#benchmarks
[nncf-jpqd-pr]: https://github.com/openvinotoolkit/nncf/pull/1319
[jpqd-examples]: https://github.com/huggingface/optimum-intel/tree/v1.7.3-release/examples/openvino
[jpqd-optimum-release]: https://github.com/huggingface/optimum-intel/releases/tag/v1.7.0
[dlbp]: https://dblp.org/pid/210/3132.html
[dhub]: https://hub.docker.com/repositories/vuiseng9
[hf]: https://huggingface.co/vuiseng9
[mlperf-t5.1-rd]: https://github.com/vuiseng9/mlperf-t5.1-rundown
[mlperf-t6.0-rd]: https://github.com/vuiseng9/mlperf-t6.0-rundown
[nv4f_mx8b_pr]: https://github.com/vuiseng9/TransformerEngine/pull/5
[faster-qat]: https://github.com/vuiseng9/faster-qat
[moelab]: https://github.com/vuiseng9/moe-lab
[moelab-gif]: https://github.com/vuiseng9/moe-lab/blob/main/assets/compare_lb_strategy_heatmaps.gif
[moelab-groupmm]: https://github.com/vuiseng9/moe-lab/blob/main/assets/grouped_vs_looped_mm.png
[nncf-mvmt]: https://github.com/openvinotoolkit/nncf/blob/release_v2190/src/nncf/experimental/torch/sparsity/movement/MovementSparsity.md
[ep-comm]: https://github.com/vuiseng9/ep-comm