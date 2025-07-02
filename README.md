# 🧪 Reaction Time Predictor from Video Frames (Multi-Reaction Support)

This project uses **computer vision and regression** to estimate the **remaining time of a chemical reaction** based on a single image frame from a video. Originally built for the **Iodine Clock Reaction**, this framework is designed to generalize to **multiple types of visible chemical reactions**.

---

## 📘 Project Summary

You are given a video of a chemical reaction — such as the Iodine Clock or any other visible reaction.

The task is:

> Given any frame from that video, predict how many seconds are left before the reaction completes.

We achieve this using:

- **CNN feature extraction** from a pretrained **ResNet18**
- A **regression model** trained on these CNN embeddings
- A complete pipeline for frame extraction, embedding, training, and inference

---

## 🔁 Workflow Overview

```mermaid
graph TD
    A[Input Reaction Video] --> B[Extract Frames]
    B --> C[ResNet18 Embedding]
    C --> D[Train Regressor]
    D --> E[Predict Time Remaining]
