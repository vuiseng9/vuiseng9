**Narrow Precision Training**
* [Quantized Training in FP4(8)][qt]: *Concepts and Reference Pytorch Implementation using cuBLASLt and Microxcaling.*
* [Unofficial][nvfp4-bench] and Early Benchmark of Nvidia's NVFP4 Training on Blackwell 8xB200.

**Distributed & Parallel**
* [Megatron, Transformed!][mtuts] *A Hands-on Megatron-LM Tutorial on Replicating Empirical Trends in Distributed Training and Model Parallelism*.
* Quick [Visual][mlperf-t5.1-rd] Rundown on MLPerf v5.1 Training, *new Llama3.1-8B, Flux.1 only*.
   
**Model Optimization for Efficient Inference**
* Post-Training Statistical Calibration for Higher Activation Sparsity,
    <small><i>[[ENLSP 2024 Spotlight 7](https://neurips2024-enlsp.github.io/), 
    [Paper](https://arxiv.org/abs/2412.07174),
    [Oral](https://neurips.cc/virtual/2024/106426),
    [Code](https://github.com/IntelLabs/SCAP),
    [Integrated](https://github.com/openvinotoolkit/nncf/blob/develop/src/nncf/experimental/torch/sparsify_activations/ActivationSparsity.md)]  </i></small>

* *Pre-LLM explosion* — [Unified HuggingFace Trainer][mlperf-i-v3-jpqd] for Joint Pruning, Quantization, and Distillation ([JPQD][nncf-jpqd-pr]), integrating OpenVINO NNCF and runtime. 16× more BERT serving throughput on Xeon Sapphire Rapids. See [MLPerf][jpqd-bench] Inference 3.0 submission. [Applicable][jpqd-examples] vision, audio models.

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
