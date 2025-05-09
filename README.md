# Tensor Parallelism

Code accompanying the deep-dive [blog post on Tensor Parallelism](https://determined.ai/blog/tp).

- MLP TP profiling code in `tp_profiling.py`

To run on 2 GPUs:
`torchrun --nproc-per-node=2 tp.py`

## Sample Benchmark Results

The table below shows V100 performance results for varying `d_model` sizes and tensor parallel degrees (`tp_degree`). Metrics include execution time (`time_s`) and throughput (`tflop_s_gpu`).

| tp_degree | d_model | time_s   | tflop_s_gpu |
|-----------|---------|----------|-------------|
| 1         | 1000    | 0.007838 | 8.3616      |
| 1         | 2000    | 0.029901 | 8.7670      |
| 1         | 3000    | 0.065187 | 9.0495      |
| 1         | 4000    | 0.104123 | 10.0706     |
| 1         | 5000    | 0.162556 | 10.0790     |
| 1         | 6000    | 0.237052 | 9.9527      |
| 1         | 7000    | 0.323475 | 9.9274      |
| 1         | 8000    | 0.419774 | 9.9918      |
| 1         | 9000    | 0.538514 | 9.8575      |
| 1         | 10000   | 0.666283 | 9.8361      |
| 2         | 1000    | 0.005214 | 6.2999      |
| 2         | 2000    | 0.016634 | 7.8780      |
| 2         | 3000    | 0.035340 | 8.3444      |
| 2         | 4000    | 0.055086 | 9.5175      |
| 2         | 5000    | 0.086082 | 9.5120      |
| 2         | 6000    | 0.121508 | 9.7042      |
| 2         | 7000    | 0.168722 | 9.5144      |
| 2         | 8000    | 0.217281 | 9.6503      |
| 2         | 9000    | 0.278880 | 9.5169      |
| 2         | 10000   | 0.340343 | 9.6269      |
