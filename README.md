# k8s-taefik-v2.2


### 1. 创建CRD资源
```
kubectl apply -f traefik-crd.yaml
```

#### 2. 创建 RBAC 权限
```
kubectl apply -f traefik-rbac.yaml -n kube-system
```

### 3. 创建 Traefik ConfigMap 资源
```
kubectl apply -f traefik-config.yaml -n kube-system
```

### 4. 给节点打标签
```
kubectl label nodes docker-desktop IngressProxy=true
```

### 4. 部署 Traefik
```
kubectl apply -f traefik-deploy.yaml -n kube-system
```

### 5. 配置路由
```
kubectl apply -f traefik-dashboard-route.yaml -n kube-system
```