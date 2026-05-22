# Interpretabilidad (SHAP/LIME)
- timestamp: 2026-05-22T15:01:11.984198
- sample_size: 500
- seed: 42
## SHAP
- status: recomputed
- plot_summary: saved
- plot_force: error: In v0.20, force plot now requires the base value as the first parameter! Try shap.plots.force(explainer.expected_value, shap_values) or for multi-output models try shap.plots.force(explainer.expected_value[0], shap_values[..., 0]).
- alignment_features_explanations: True
- stability_jaccard_top20: 1.0
- top_features: span_days, reply_rate, posts_total_temporal
## LIME
- status: computed
## Analisis local vs global
- global_ok: True
- local_ok: True
- runtime_seconds: 17.49