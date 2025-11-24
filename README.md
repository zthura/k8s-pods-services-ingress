 Project Objectives 
- Multi‑App Deployment → App A နဲ့ App B ဆိုပြီး application နှစ်ခုကို Kubernetes cluster ထဲမှာ run လုပ်မယ်။
- Multi‑Container Pods → Pod တစ်ခုထဲမှာ Main container (application logic) နဲ့ Sidecar container (monitoring/logging) နှစ်ခု run လုပ်မယ်။
- Networking & Exposure → Service (ClusterIP + NodePort) နဲ့ Ingress သုံးပြီး Pod တွေကို expose လုပ်မယ်။
- Observability → Prometheus + Grafana သုံးပြီး metrics, logs, dashboards တွေ configure လုပ်မယ်။
- Auto Load Balancing & Scaling → Deployment + Horizontal Pod Autoscaler (HPA) သုံးပြီး traffic load balancing နဲ့ Pod count auto adjust လုပ်မယ်။
- GitOps Style Repo → GitHub repo ထဲမှာ manifests တွေကို folder structure နဲ့ organize လုပ်ပြီး reproducible lab တစ်ခုအဖြစ်သိမ်းမယ်။

Learn from this project
- Kubernetes Basics
- Pod manifest writing (YAML/JSON)
- Multi‑container Pod pattern (sidecar design)
- Networking Concepts
- Service types (ClusterIP, NodePort)
- Ingress routing (domain‑based access)
- Deployment Strategies
- Using Deployment for replica management
- Rolling updates & self‑healing
- Scaling & Load Balancing
- Horizontal Pod Autoscaler (HPA)
- Service round‑robin traffic distribution
- Monitoring & Observability
- Prometheus scrape configs
- Grafana dashboards & datasources
- GitOps & Repo Management
- Organizing manifests in GitHub repo
- Declarative vs imperative resource creation

Test from this project
- ✅ Pod Creation → Verify Pods with multiple containers run correctly.
- ✅ Service Connectivity → Test if traffic is routed to Pods via Service.
- ✅ Ingress Routing → Access apps via domain (app-a.local, app-b.local).
- ✅ Load Balancing → Send multiple requests and confirm traffic is distributed across Pods.
- ✅ Auto Scaling → Stress test CPU usage and check if HPA scales Pods up/down.
- ✅ Monitoring → Check Prometheus metrics and Grafana dashboards for visibility.
- ✅ Failure Recovery → Kill one Pod and confirm Service routes traffic to healthy Pods.
- ✅ Repo Workflow → Apply manifests from GitHub repo and confirm reproducibility.


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

# Deploy App A & B
kubectl apply -f app-a/deployment-a.yaml
kubectl apply -f app-a/service-a.yaml
kubectl apply -f app-b/deployment-b.yaml
kubectl apply -f app-b/service-b.yaml

# Deploy Ingress
kubectl apply -f ingress/ingress.yaml

# Deploy Monitoring
kubectl apply -f monitoring/prometheus-config.yaml
kubectl apply -f monitoring/grafana-config.yaml

# Deploy Auto Scaling
kubectl apply -f scaling/hpa-a.yaml
kubectl apply -f scaling/hpa-b.yaml
