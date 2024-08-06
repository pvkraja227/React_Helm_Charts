### Server_Deploy

(Install Helm - 3)

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3

chmod 700 get_helm.sh

./get_helm.sh

helm create react-helm / cd react-helm / ls (Chart.yaml, Charts, templates, values.yaml)

since we created namespace, update deployment/service/ingress in templates folder with namespace: {{ .Values.namespace }} under meta-data

now by using our own created deployment/service/ingress  --> modify accordingy in values.yaml and add namespace: react-nginx under replicasets

kubectl config view (o/p port - 16443)

kubectl install react-helm . --dry-run (o/p port 16443, k8s at 8080 --> so, error)

kubectl config view --raw>~/.kube/config

chmod 600 ~/.kube/config

kubectl install react-helm . --dry-run

kubectl install react-helm . (o/p revision:1)

kubectl upgrade react-helm . (change a value, o/p revision:2)

helm list

kubectl get pods -n react-nginx (pods just started)

helm history react-helm

helm rollback react-helm 1 (back to revision:1)

helm uninstall react-helm
