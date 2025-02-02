```
user@kube-v3-2-1-nllao:~$ kubectl get role test-role -n test-rbac -o yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"rbac.authorization.k8s.io/v1","kind":"Role","metadata":{"annotations":{},"creationTimestamp":null,"name":"test-role","namespace":"test-rbac"},"rules":[{"apiGroups":[""],"resources":["serviceaccounts"],"verbs":["create","get","list","patch","update","watch"]},{"apiGroups":[""],"resources":["pods"],"verbs":["get","list","watch"]},{"apiGroups":[""],"resources":["rolebindings"],"verbs":["delete","deletecollection","get","list","watch"]}]}
  creationTimestamp: "2025-02-02T14:24:45Z"
  name: test-role
  namespace: test-rbac
  resourceVersion: "5622"
  uid: c23f46a8-e5b2-4acb-8662-eab71d227d87
rules:
- apiGroups:
  - ""
  resources:
  - serviceaccounts
  verbs:
  - create
  - get
  - list
  - patch
  - update
  - watch
- apiGroups:
  - ""
  resources:
  - pods
  verbs:
  - get
  - list
  - watch
- apiGroups:
  - ""
  resources:
  - rolebindings
  verbs:
  - delete
  - deletecollection
  - get
  - list
  - watch

user@kube-v3-2-1-nllao:~$ kubectl get rolebinding test-binding -o yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"rbac.authorization.k8s.io/v1","kind":"RoleBinding","metadata":{"annotations":{},"creationTimestamp":null,"name":"test-binding","namespace":"default"},"roleRef":{"apiGroup":"rbac.authorization.k8s.io","kind":"Role","name":"test-role"},"subjects":[{"kind":"ServiceAccount","name":"test-user","namespace":"test-rbac"}]}
  creationTimestamp: "2025-02-02T14:25:30Z"
  name: test-binding
  namespace: default
  resourceVersion: "5694"
  uid: 22f76dde-7a7a-43ff-a792-0ccad5ba8394
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: Role
  name: test-role
subjects:
- kind: ServiceAccount
  name: test-user
  namespace: test-rbac


```
