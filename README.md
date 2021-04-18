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
* You have to manually set `reclaimPolicy` to `Retain` on the `hcloud-csi`
* You have to rename the secret `hcloud-csi` uses to `hcloud`, because this secret is alerady present on the cluster
