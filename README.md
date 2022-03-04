# kubebuilder-guestbook-debug

Simple kubebuilder get-started project `guestbook`, added one spec field with unstructured.Unstructured type which breaks the operator.

### start
```
make deploy-local
```

### apply the CR
```
kubectl apply -f config/samples/webapp_v1_guestbook.yaml
```

### observe the error in the log
```
W0304 22:36:45.381904       1 reflector.go:442] pkg/mod/k8s.io/client-go@v0.23.0/tools/cache/reflector.go:167: watch of *v1.Guestbook ended with: an error on the server ("unable to decode an event from the watch stream: unable to decode watch event: Object 'Kind' is missing in '{}'") has prevented the request from succeeding
W0304 22:36:46.399073       1 reflector.go:324] pkg/mod/k8s.io/client-go@v0.23.0/tools/cache/reflector.go:167: failed to list *v1.Guestbook: Object 'Kind' is missing in '{}'
E0304 22:36:46.399252       1 reflector.go:138] pkg/mod/k8s.io/client-go@v0.23.0/tools/cache/reflector.go:167: Failed to watch *v1.Guestbook: failed to list *v1.Guestbook: Object 'Kind' is missing in '{}'
W0304 22:36:48.272865       1 reflector.go:324] pkg/mod/k8s.io/client-go@v0.23.0/tools/cache/reflector.go:167: failed to list *v1.Guestbook: Object 'Kind' is missing in '{}'
E0304 22:36:48.272924       1 reflector.go:138] pkg/mod/k8s.io/client-go@v0.23.0/tools/cache/reflector.go:167: Failed to watch *v1.Guestbook: failed to list *v1.Guestbook: Object 'Kind' is missing in '{}'
```
