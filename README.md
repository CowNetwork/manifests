manifests
=========

Here live our Kubernetes manifests for all our clusters.

Directory layout

```
manifests
├── README.md
└── <project>
     └──<cluster>
        └── <namespace>
            └── <what>.<kind>.yaml
```

**Important things to note**
* I manually set `reclaimPolicy` to `Retain` on the `hcloud-csi`
* I renamed the secret `hcloud-csi` uses to `hcloud`, because this secret is alerady present on the cluster
* I explicitly set `nodePort: 30443` for https and `nodePort: 30080` for http traffic 
  in order to have fixed ports on every worker node to make configuring the hcloud loadbalancer easier 
