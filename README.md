# Singer or Studio?

This repository gives coauthors the experimental record for the paper on production mismatch in singer retrieval. The central comparison holds the query and genuine candidate fixed and changes only the impostor's processing. With a dry JVS-MuSiC query and a synthetic-reverberant genuine candidate, CVSM-ART ranking error fell from **46.24% to 17.52%** when the impostor received the same processing recipe. The paired reduction was **28.72 percentage points**. This is a controlled ranking result for a named encoder, cohort and treatment.

## Start here

1. Read the [claim-to-evidence map](docs/CLAIMS.md) for the paper's scope, strongest results and limits.
2. Read the [journal draft PDF](manuscript/Singer%20or%20Studio%20-%20When%20Production%20Changes%20the%20Match.pdf), [editable draft](manuscript/when_production_changes_the_match.md) and [technical supplement](evidence/supplement.md). The [professor copy](manuscript/Singer%20or%20Studio%20-%20The%20Thesis.pdf) explains the experiments in more detail. The journal draft and this repository use the corrected shared-condition confidence intervals.
3. Follow [reproduction](docs/REPRODUCTION.md) to verify the scores first, then [dataset and model setup](docs/DATA-AND-MODELS.md) for a waveform-to-score rerun.

```sh
python -m pip install -r requirements-audit.txt
python evidence/verify_results.py
python evidence/verify_core_counts.py
```

The first check recalculates JVS rankings and point contrasts from preserved trial-level cosine scores. The second reconstructs all 200 core model-condition trial masks and rates from the crop manifests and saved singer error counts. It also reproduces all ten shared-condition intervals. Both checks work without audio or model downloads.

| Directory | Contents |
| --- | --- |
| [manuscript](manuscript/) | Reading copies, editable text, figures and build scripts |
| [evidence](evidence/) | Exact result tables, score-level evidence, input manifests, protocols and verification scripts |
| [workflow](workflow/) | Portable model fetch, crop rendering, embedding and scoring commands |
| [archive](archive/) | Source analysis scripts, original outputs, selected-inference recheck, auxiliary method and artist-level records |
| [docs](docs/) | Claim map, setup, literature notes, model hashes, validation and [import history](docs/HISTORY.md) |

Audio, embeddings, private training assets and large checkpoint files belong in ignored local directories. The released encoders are fetched from their upstream sources and verified by hash. The optional Yakura and fine-tuning baseline weights are author-local, with archived results available here. This paper's evidence is machine-only. Participant responses and listening-study material are outside its scope.


## Contributors
Desu Nayanika Sri Sai Jhansi [https://github.com/desunayani-ssj] \
Shivani Kona [https://github.com/shivani11-glitch]
Venkata Sathvik Chittipaka [https://github.com/sathvikchitti]
