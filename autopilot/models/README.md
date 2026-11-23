# Deployed model: balloon_drone_v2

This is the detector that was running on AWRAS 1.3's Raspberry Pi 5 at HackUMass XIV, copied straight off the Pi.

| File | What it is |
| --- | --- |
| `balloon_drone_v2/best.pt` | Trained YOLO11n weights (PyTorch, laptop only) |
| `balloon_drone_v2/ncnn_640x480/` | NCNN export the Pi runs by default, about 13 fps |
| `balloon_drone_v2/ncnn_416x320/` | Smaller NCNN export, a faster fallback |

Classes: `0: balloon`, `1: drone`.

v2 is the v1 drone and balloon model retrained with balloons against open sky. How it was trained, filtered and tested is in [`docs/runbook-task08-ml-detector.md`](../docs/runbook-task08-ml-detector.md).

Run it on the Pi with:

```
python3 tools/web_preview.py --mode hybrid --model-path models/balloon_drone_v2/ncnn_640x480
```

The weights come from Ultralytics YOLO11n, which is licensed under AGPL-3.0 (see each export's `metadata.yaml`).
