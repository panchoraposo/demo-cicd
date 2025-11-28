oc adm policy add-cluster-role-to-user cluster-admin -z openshift-gitops-argocd-application-controller -n openshift-gitops

oc patch argocd openshift-gitops \
  -n openshift-gitops \
  --type='merge' \
  -p='{"spec": {"kustomizeBuildOptions": "--enable-helm"}}'