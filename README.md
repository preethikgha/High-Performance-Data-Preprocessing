## High-Performance Data Preprocessing Using Parallel Programming in Python  

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Dask](https://img.shields.io/badge/Dask-Parallel_Processing-orange?logo=dask)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-green?logo=pandas)
![Colab](https://img.shields.io/badge/Platform-Google_Colab-yellow?logo=googlecolab)

---

###  Overview  
This project benchmarks **serial vs. parallel data preprocessing** workflows using **Pandas** and **Dask** on the Amazon Fine Food Reviews dataset..  
With growing data volumes, preprocessing becomes a performance bottleneck in AI/ML pipelines.  
This project showcases how **parallel computing** using Dask can significantly reduce runtime and improve scalability across large datasets.

---

###  Objectives  
- Compare the performance of serial (Pandas) vs parallel (Dask) data preprocessing.  
- Quantify runtime improvements at different data scales.  
- Demonstrate text cleaning and transformation as a real-world preprocessing workload.  
- Highlight the advantages of parallel execution and distributed computation for large-scale ETL.

---

###  Tech Stack  
| Category | Tools / Libraries |
|-----------|-------------------|
| Language | Python 3.10 |
| Data Processing | Pandas, Dask |
| Parallel Programming | multiprocessing, dask.delayed |
| Visualization | Matplotlib, Seaborn |
| Environment | Google Colab  |
|DATASET | https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews|
---
### Data Preprocessing Workflow  
The text preprocessing pipeline applies a sequence of NLP transformations to both `Summary` and `Text` columns:  
1. Lowercasing text  
2. Removing non-alphabetic characters using Regular Expressions  
3. Tokenizing using `nltk.word_tokenize()`  
4. Removing stopwords (`a, an, the, is, are, in, on, and, or`)  
5. Applying stemming using `PorterStemmer`  
6. Rejoining processed tokens into cleaned strings  

Parallel execution is implemented with Dask, while Pandas performs the same logic serially for baseline comparison.

---

###  Performance Results  

| Rows    | Serial (Pandas) | Parallel (Dask) |
| ------- | --------------- | --------------- |
| 30,000  | 48.05 sec       | 52.45 sec       |
| 100,000 | 171.30 sec      | 54.38 sec       |
| 200,000 | 327.33 sec      | 51.93 sec       |

 **Key Insights:**  
- For smaller datasets, Dask’s parallel setup introduces slight overhead.  
- At larger scales, Dask achieves **6× faster performance** and maintains consistent runtimes.  
- Pandas scales linearly with data size, while Dask distributes the load across multiple cores efficiently.

>  **Conclusion:** Dask outperforms Pandas significantly for medium to large datasets, proving the impact of parallel programming on preprocessing pipelines.

---

###  Core Concepts Demonstrated  
- Parallel data partitioning and lazy evaluation with Dask  
- Multiprocessing vs multithreading behavior in ETL pipelines  
- Performance profiling using `time` and `%timeit`  
- Efficient text cleaning for NLP workflows  
- Visual performance comparison between serial and parallel execution  

---

###  Visual Insights  
**Pandas:** CPU-bound, sequential, scales poorly with large datasets  
**Dask:** Multi-core execution, consistent runtime, better memory utilization  
**Result:** Dask consistently delivers optimized performance for large-scale text preprocessing  

---

###  Future Enhancements  
- Integrate **Modin** and **Ray** for advanced distributed dataframes  
- Add **GPU-accelerated preprocessing** via RAPIDS cuDF  
- Expand benchmarks to cloud-scale datasets using **Azure ML / AWS Sagemaker**

---

###  Author  
**Preethikgha M**  
