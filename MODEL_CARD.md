
# Model card

## Architecture

Each trait is fitted independently. The final prediction combines a fold-safe
cultivar-aware PLS anchor, a compact residual spectral CNN and a nested RBF-SVR
expert selected using training-internal information. The network receives 228 NIR
bands; test labels never enter preprocessing or selection.

## Evaluation

Five frozen cultivar-stratified outer folds yield 58,206 OOF predictions. Reported
R² is 0.827 for fruit weight, 0.629 for SSC, 0.544 for pH and 0.502–0.719 across the
nine texture endpoints. Performance inside the registered domain must not be
interpreted as external transfer.

## Calibration and failure modes

The held-batch audit covers five batches from two cultivars. Twenty to forty labelled
reference fruit captured most observed adaptation benefit. Zero-shot leave-one-
cultivar-out texture regression failed on cultivar-macro evaluation. A deployment
must detect domain changes and request calibration rather than silently extrapolate.

## Weight status

`pending_final_refit`: no public weight file is claimed. A valid release must bind
architecture, preprocessing, cultivar registry, trait registry, training-data digest,
framework versions and serialized prediction replay to each weight SHA-256.
