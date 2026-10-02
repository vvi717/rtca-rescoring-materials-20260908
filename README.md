# Prediction-rescoring material

Companion material for **Readout Fitting for Low-Data Turn-Taking Preference Prediction: A Diagnostic Study** by **Wei Liu**.

Download `rtca_anonymous_supplement.zip`. It contains saved predictions, hashed split and position manifests, pinned public annotation sources, a standalone NumPy scoring script, and license notices. It contains no original dialogue text, original vote labels, or model weights. The historical archive filename and anonymous access URL are retained; the camera-ready materials identify the author for attribution.

ZIP SHA256:

`15b5f94b3f2647a098670dfddfdeff836f755d159711314e526d2010f4c92db5`

After extracting the archive, use Python 3.10 or later:

```sh
python -m pip install -r requirements.txt
python score.py --fetch --output rescored.json
```

Use a fresh output filename if it already exists. `--fetch` obtains the fixed public annotations from their original source and verifies their hashes; it does not upload anything. For an existing local copy, replace `--fetch` with `--data-dir /path/to/dataset-root`.

Expected success message:

```text
PASS: 420 dialogue assignments, 3244 test positions, 28 outputs; max error 0
```

The package supports rescoring the common-split results and final sensitivity contrasts. It does not retrain encoders, refit calibrators, reproduce model selection, or execute the earlier full-120-dialogue diagnostic. The 300 test dialogues were inspected during development; successful rescoring is not independent scientific confirmation.

## Licenses

Copyright (c) 2026 Wei Liu, for the author's original contributions.

- The scoring code (`score.py`) is licensed under MIT; see `LICENSE-MIT.txt` inside the ZIP.
- The author's saved predictions, documentation and accompanying metadata are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); see `LICENSE-CC-BY-4.0.txt` and the file-by-file scope in the ZIP's README. This outer README is also licensed under CC BY 4.0.
- Upstream data, models and third-party software retain their own licenses. These notices grant only rights held by the author and do not relicense DuplexGen or its source corpora.

Attribution: Wei Liu (2026), *Readout Fitting for Low-Data Turn-Taking Preference Prediction: A Diagnostic Study*, prediction-rescoring supplement. Retain attribution and applicable license notices, and indicate changes.

## Camera-ready update

This update adds license notices and revises documentation. The scoring script, saved predictions, positions, split manifest, source manifest, expected results and requirements are byte-identical to the original submission supplement. No experimental results were changed. The earlier snapshot remains in the source repository's version history.
