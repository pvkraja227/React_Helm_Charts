### Server_Deploy

(Install Helm - 3)

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3

chmod 700 get_helm.sh

./get_helm.sh

helm create react-helm / cd react-helm / ls (Chart.yml, Charts, templates, values.yaml)

since we used/created namespace: react-nginx, update in all 3 in templates with namespace: {{ .Values.namespace }}

now by using deployment/service/ingress  - - modify accordingy in values.yaml



