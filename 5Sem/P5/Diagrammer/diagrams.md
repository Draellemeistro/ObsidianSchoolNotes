# Mermaid.js diagram code
## Kubernetes Arch...??
![[mermaid-diagram-2024-12-18-080006.svg]]
### Code
```
flowchart LR
 subgraph cluster["cluster"]
        ingress["Ingress"]
        pod1["Pod"]
        service["Malware AI svc"]
        pod2["Pod"]
        pod3["Pod"]
        service2["Keystroke AI svc"]
        pod4["Pod"]
        pod5["Pod"]
        service3["NixOS Remote Builder svc"]
  end
    client1(["backend"]) -. "Ingress-managed <br> load balancer" .-> ingress
    client(["client"])-->client1
    client2(["Raspberry Pi"])-->client1
    ingress -- /malpredict --> service
    ingress -- "/keystroke-ai" --> service2
    ingress -- "/config-nix" --> service3
    service --> pod1 & pod2
    service2 --> pod3 & pod4
    service3 --> pod5
    client2-->pod5

     ingress:::k8s
     pod1:::k8s
     service:::k8s
     service2:::k8s
     service3:::k8s
     pod2:::k8s
     pod3:::k8s
     pod4:::k8s
     pod5:::k8s
     client:::plain
     client1:::plain
     client2:::plain
    classDef plain fill:#ddd,stroke:#fff,stroke-width:4px,color:#000
    classDef k8s fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff
    classDef cluster fill:#fff,stroke:#bbb,stroke-width:2px,color:#326ce5
```


## ss



## ssssss