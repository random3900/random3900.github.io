---
layout: post
title: "ML Deployment Notes"
date: 2025-02-08 00:00:00
categories: ML
---

# ML Deployment

*This blog contains my notes of Chapter 7. Model Deployment and Prediction Service from [Designing Machine Learning Systems by Chip Huyen](https://learning.oreilly.com/library/view/designing-machine-learning/9781098107956/).*

**Serialization -** converting the model into a format that can be used by another application. Two parts that can be exported - model definition and model's parameter values. Ex. `tf.keras.Model.save()` or `torch.onnx.export()`.

**Inference -** the process of generating predictions.

## Machine Learning Deployment Myths

![ML Deployment Myths](https://raw.githubusercontent.com/groopav/random3900.github.io/refs/heads/main/images/MLDeploymentMyths.png)

## Batch Prediction Versus Online Prediction

![Prediction](https://raw.githubusercontent.com/groopav/random3900.github.io/refs/heads/main/images/Prediction.png)

Two components are required to improve online prediction latency:

- Real-time pipeline that can work with incoming data, extract streaming features, input them into a model, and return a prediction in near real time. 
- A model that can generate predictions at a speed acceptable to its end users. For most consumer apps, this means milliseconds.

## Optimization

![Optimization](https://raw.githubusercontent.com/groopav/random3900.github.io/refs/heads/main/images/Optimization.png)