# Anonymous rescoring material

Companion material for **Readout Fitting for Low-Data Turn-Taking Preference Prediction**.

Download `rtca_anonymous_supplement.zip`. It contains saved predictions, hashed split and position manifests, pinned public annotation sources, and a standalone NumPy scoring script. It contains no dialogue text, original vote labels, model weights, or author information.

ZIP SHA256:

`a14e31b82ba689219d24350bf989d6dc7353ba15866e303dc96ea47b9c290f1c`

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

The ZIP is the unchanged, hash-verified submission snapshot. Its internal README describes the original local packaging and intended submission attachment. This outer README explains access through the anonymous repository when hosted; the scoring procedure and scientific scope are unchanged.
