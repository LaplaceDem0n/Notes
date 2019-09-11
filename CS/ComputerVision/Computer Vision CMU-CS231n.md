# Computer Vision CMU-CS231n

# 简介

人在看到图片的时候有很复杂的处理，计算机视觉只能做到其中的很小一部分。

# 一些被抛弃的方法

## K近邻方法

### 定义

训练：记忆

推断：比较L1/L2距离（曼哈顿距离与欧几里得距离）

### Pros

Easy

### Cons

1.  $O(1)$ train, $O(n)$ inference
2.  Not robust to tint/shift/etc.

### Tips

Hyperpara-> k times k fold validation.

Data set->Train/validation/test.