1- helm repo add elastic https://helm.elastic.co --namespace logging   (pour ajouter le repo elastic qui contient notre services)
  ## on crée les fichier de configuration de elasticsearche elasticsearch-values.yaml
2- helm install elasticsearch elastic/elasticsearch -f elasticsearch-values.yaml
  ## cette commande install elasticsearch avec les configuration spécifie dans le fichier elasticsearch-values.yaml

  ## comme ça on fait pour chaque service, les fichier de configuration vous les trouvez dans les dossier dédié pour chaque service  
3- helm install filebeat elastic/filebeat -f filebeat-values.yaml

4- helm install logstash elastic/logstash -f logstash-values.yaml

5- helm install kibana elastic/kibana -f kibana-values.yaml

######

6- $ kubectl get secret elasticsearch-master-credentials -o jsonpath="{.data.username}" | base64 --decode

$ kubectl get secret elasticsearch-master-credentials -o jsonpath="{.data.password}" | base64 --decode
#### ces commande pour générer le login et mot de passe affin d'accéder à l'interface graphique kibana


## N.B:
---n'oublie pas d'autoriser les port des services depuis les règle de parfeu (GCP)---
 
