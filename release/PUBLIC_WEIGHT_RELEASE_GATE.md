
# Public weight release gate

For every trait: refit the frozen architecture on the approved full-data cohort;
record seed, environment, training-data manifest and preprocessing; save anchor,
kernel expert, CNN state and cultivar offsets; verify a fixed inference fixture on CPU
and GPU; compute SHA-256; then freeze an immutable model version. A missing or failed
trait blocks the public claim that the complete 12-output model is released.
