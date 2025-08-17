# Building Efficient Input Pipelines with `tf.data`

## 1. Project Title

**High-Performance Data Pipelines in TensorFlow using `tf.data`**

---

## 2. Problem Statement and Goal of Project

Efficient data loading and preprocessing are critical for training deep learning models at scale.
The goal of this project is to **demonstrate best practices for building high-performance input pipelines** with TensorFlow’s `tf.data` API, enabling faster training and optimal hardware utilization.

---

## 3. Solution Approach

The notebook follows a step-by-step approach to constructing `tf.data` pipelines:

1. **Dataset creation** – Build datasets from in-memory arrays, tensors, and file sources.
2. **Data transformation** – Apply mapping functions for preprocessing (e.g., normalization, resizing).
3. **Shuffling and batching** – Randomize data order and group into mini-batches for training.
4. **Performance optimization** – Use `cache()`, `prefetch()`, and `AUTOTUNE` to reduce input bottlenecks.
5. **Iteration and inspection** – Loop through datasets to validate contents and preprocessing logic.

---

## 4. Technologies & Libraries

From the code:

* **TensorFlow** – `tf.data` API for dataset creation, transformation, and performance tuning.
* **NumPy** – Generating synthetic data for demonstration.

---

## 5. Description about Dataset

**Not provided** – The notebook demonstrates pipelines using synthetic data arrays and tensors.

---

## 6. Installation & Execution Guide

**Requirements:**

```bash
pip install tensorflow numpy
```

**Run the notebook:**

```bash
jupyter notebook tf_data.ipynb
```

or in JupyterLab:

```bash
jupyter lab tf_data.ipynb
```

Execute cells sequentially to reproduce the pipeline demonstrations.

---

## 7. Key Results / Performance

* Created pipelines from multiple data sources (arrays, tensors, files).
* Applied preprocessing transformations directly in the dataset pipeline.
* Implemented shuffling, batching, and prefetching to improve throughput.
* Demonstrated `AUTOTUNE` for dynamic performance optimization.

Example snippet:

```python
dataset = tf.data.Dataset.from_tensor_slices((features, labels))
dataset = dataset.shuffle(1000).batch(32).prefetch(tf.data.AUTOTUNE)
```

---

## 8. Screenshots / Sample Out

**Pipeline with batching and prefetching:**

```
<BatchDataset shapes: ((None, 28, 28), (None,)), types: (tf.float32, tf.int64)>
```

**Iterating through dataset:**

```
Features: tf.Tensor([...], shape=(32, 28, 28), dtype=float32)
Labels: tf.Tensor([...], shape=(32,), dtype=int64)
```

---

## 9. Additional Learnings / Reflections

* `tf.data` allows flexible and composable data transformations directly in TensorFlow graphs.
* Prefetching and caching greatly improve GPU utilization during training.
* Using `AUTOTUNE` automates performance tuning without manual buffer sizing.
* A well-designed input pipeline can significantly reduce training time for large datasets.

> 💡 *Some interactive outputs (e.g., plots, widgets) may not display correctly on GitHub. If so, please view this notebook via [nbviewer.org](https://nbviewer.org) for full rendering.*

---

## 👤 Author

**Mehran Asgari**
**Email:** [imehranasgari@gmail.com](mailto:imehranasgari@gmail.com)
**GitHub:** [https://github.com/imehranasgari](https://github.com/imehranasgari)

---

## 📄 License

This project is licensed under the Apache 2.0 License – see the `LICENSE` file for details.

---
