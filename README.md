## Model Comparison: PyTorch vs TensorFlow

This project compares PyTorch and TensorFlow implementations of a structurally equivalent GRU-based encoder–decoder model for NFL player trajectory prediction.

Both models share identical architectures (2-layer GRU encoder–decoder), parameter counts, optimization settings, and random seeds.

Despite this, their autoregressive inference behavior diverges significantly.

## Key Results

Validation RMSE

PyTorch: 1.55

TensorFlow: 19.47

Submission-level comparison (5,837 paired predictions)

Mean prediction gap: 22.65 yards

Max gap: 79.32 yards

Low inter-model correlation (x: 0.27, y: 0.50)

## Interpretation

The divergence is consistent with known sequence modeling issues:

Exposure Bias from teacher forcing (Bengio et al., 2015)

Hidden-state mismatch under autoregressive inference (Goyal et al., 2016)

Error accumulation over long horizons (He et al., 2020)

These results highlight that structural equivalence does not guarantee functional equivalence in autoregressive sequence models.

## References

Bengio et al., Scheduled Sampling for Sequence Prediction with RNNs, NeurIPS 2015

Goyal et al., Professor Forcing, NeurIPS 2016

He et al., Quantifying Exposure Bias for Neural Language Generation, ACL 2020
