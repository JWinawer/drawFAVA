# Cortical sulcus labels (fsaverage)

These files come from the Natural Scenes Dataset (NSD) bucket,
`nsddata/freesurfer/fsaverage/label/` (Kendrick Kay):

- `lh.corticalsulc.mgz`, `rh.corticalsulc.mgz`: one label per fsaverage
  vertex (0 = none, 1-28 = a sulcus or gyrus).
- `corticalsulc.mgz.txt`: the name of each label number.

`docker-compose.yml` mounts this folder at `/home/jovyan/datasets/sulci`.
`config/nod.yaml` and `config/nsd.yaml` use it to draw a "sulci" panel (the
subject's curvature with sulcus outlines and names). If the folder is missing,
the panel shows the curvature only.

All NOD and NSD subjects in DrawFAVA are stored on fsaverage vertices, so the
same labels apply to every subject. The NSD per-subject `corticalsulc` files
are these fsaverage labels moved onto each subject, so they add nothing new.
These are atlas labels: small, variable sulci (for example ptCoS, mFus, OTS)
can miss a subject's own folds, so check them against the curvature.
