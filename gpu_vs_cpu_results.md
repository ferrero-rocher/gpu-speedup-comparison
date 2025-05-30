
# 📊 GPU vs CPU Performance Benchmark

This report summarizes the runtime performance comparisons between native Python code and GPU-accelerated code using Numba for three core computations: matrix multiplication, vector addition, and sum reduction. All tests were run on Google Colab using a T4 GPU.

---

## 🔢 Matrix Multiplication

![alt text](image.png)

| Matrix Size | GPU Time (s) | CPU Time (s) |
|-------------|--------------|--------------|
| 100 x 100   | 0.137        | 0.940        |
| 250 x 250   | 0.150        | 15.903       |
| 500 x 500   | 0.128        | 128.590      |

In summary, the table compares execution times (in seconds) between GPU-accelerated code and native Python code across input sizes of 100, 250, and 500. The GPU code consistently demonstrates faster execution times than native Python code, with values ranging from 0.137 to 0.128 seconds for the GPU code and 0.940 to 128.59 seconds for native Python code.

**Insight:** GPU acceleration shows exponential performance gain as matrix size increases, with up to ~1000x speedup at size 500.

---

## ➕ Vector Addition

![alt text](image-1.png)

| Vector Size   | GPU Time (s) | CPU Time (s) |
|---------------|--------------|--------------|
| 1,000,000     | 0.159        | 0.500        |
| 10,000,000    | 0.194        | 3.090        |
| 100,000,000   | 1.041        | 33.417       |

In summary, the table compares execution times (in seconds) between GPU-accelerated code and native Python code across input sizes of 1000000, 10000000, and 100000000. The GPU code consistently demonstrates faster execution times than native Python code, with values ranging from 0.159 to 1.041 seconds for the GPU code and 0.500 to 33.417 seconds for native Python code.

**Insight:** GPU is over 30x faster at the largest scale. This demonstrates efficient parallel processing for element-wise operations.

---

## ➗ Sum Reduction
![alt text](image-2.png)

| List Size     | GPU Time (s) | CPU Time (s) |
|---------------|--------------|--------------|
| 1,000,000     | 0.159        | 0.500        |
| 10,000,000    | 0.194        | 3.090        |
| 100,000,000   | 1.041        | 33.417       |

**Insight:** Similar to vector addition, sum reduction benefits heavily from GPU's ability to parallelize aggregation operations.

---

## 🎯 Conclusion

- GPU acceleration via Numba offers **significant runtime improvements** across all three operations.
- Performance gain **scales with input size**, making it a valuable optimization for large datasets.
- This experiment highlights the power of **parallelism and CUDA threading**, especially for data-heavy computations.

