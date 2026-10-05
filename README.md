# Color-Invariant Saree Design Recognition

A PyTorch-based computer vision system for recognizing saree surface designs while reducing dependence on color palette.

## Approach

The system uses an ImageNet-pretrained ResNet-18 backbone with a 256-dimensional L2-normalized embedding head. Strong color augmentation and NT-Xent contrastive learning encourage the model to focus on stable textile structure rather than palette.

## Pipeline

Saree Image
→ ResNet-18
→ 256-D Embedding
→ Cosine Similarity
→ Gallery Ranking

## Evaluation

Controlled synthetic-colorway retrieval:

- Top-1 Accuracy: 98.33%
- Top-5 Accuracy: 100.00%
- MRR: 0.9917
- Mean Positive Rank: 1.02
- Mean Positive Similarity: 0.9338

Verification diagnostic:

- Positive Similarity: 0.9338
- Hard-Negative Similarity: 0.1531
- Similarity Margin: 0.7807

## Efficiency

- Parameters: 11.57M
- Embedding Dimension: 256
- Checkpoint Size: 44.23 MB
- CPU Latency: 32.80 ms/image
- CPU Throughput: 30.5 images/sec

## Dataset

The notebook uses the Indian Saree Patterns dataset and the DeepLure saree corpus.

The proprietary DeepLure corpus is not redistributed in this repository.

## Evaluation Note

The reported retrieval results are from a controlled synthetic-colorway benchmark. They should not be interpreted as general real-world saree design recognition accuracy because reliable individual design identity labels and natural colorway pairs were unavailable.

## Reproducibility

The complete training and evaluation workflow is provided in the Jupyter notebook.

The ResNet-18 backbone uses official ImageNet-pretrained weights.
