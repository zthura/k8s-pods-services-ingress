# k8s-pods-services-ingress
Labs

- App A → 2 Pods, each Pod has 2 containers (Main + Sidecar)
- App B → 2 Pods, each Pod has 2 containers (Main + Sidecar)
- Services → ClusterIP + NodePort for internal/external access
- Ingress → Domain‑based routing (app-a.local, app-b.local)
- Monitoring → Sidecars (Prometheus, Grafana agent)

