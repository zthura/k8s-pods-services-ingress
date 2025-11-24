# k8s-pods-services-ingress
Labs

- App A → 2 Pods, each Pod has 2 containers (Main + Sidecar)
- App B → 2 Pods, each Pod has 2 containers (Main + Sidecar)
- Services → ClusterIP + NodePort for internal/external access
- Ingress → Domain‑based routing (app-a.local, app-b.local)
- Monitoring → Sidecars (Prometheus, Grafana agent)
Command to run
# Apply Pods
kubectl apply -f app-a/pod-a1.yaml
kubectl apply -f app-a/pod-a2.yaml
kubectl apply -f app-b/pod-b1.yaml
kubectl apply -f app-b/pod-b2.yaml

# Apply Services
kubectl apply -f app-a/service-a.yaml
kubectl apply -f app-b/service-b.yaml

# Apply Ingress
kubectl apply -f ingress/ingress.yaml
