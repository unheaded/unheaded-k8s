# unheaded-k8s

Kubernetes material for Unheaded: manifests, a Helm chart, ArgoCD apps and a kind lab. **A lab component, not a product target** (DP-17): the platform scales from one host to many without it. No cluster runs anywhere; ADR-055 keeps k3s off west and east.

Moved out of `unheaded/unheaded` on 2026-11-04 with its history.

- `kubernetes/manifests/`, `deploy/k8s/`, `deploy/argocd/`: manifests and apps
- `helm/unheaded/`: the chart
- `scripts/check-helm-security.sh`: every rendered container runs read-only
- `scripts/well/render-k8s-initdb.py`: renders the Well's ConfigMap from `db/` in a sibling `unheaded` checkout (`UNHEADED_REPO` overrides)
- `docs/labs/`: the lab plan

`kubernetes/manifests/overlays/gpu-vllm` is parked with vLLM (DP-713): it needs a better GPU.

uid numbers come from `pkg/uids` in the main repository; the test that held manifests to it stayed behind when these files left.
