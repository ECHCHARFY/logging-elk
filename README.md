helm repo add elastic https://helm.elastic.co --namespace logging   (pour ajouter le repo elastic qui contient notre services)
on crée les fichier de configuration de elasticsearche elasticsearch-values.yaml
helm install elasticsearch elastic/elasticsearch -f elasticsearch-values.yaml
cette commande install elasticsearch avec les configuration spécifie dans le fichier elasticsearch-values.yaml

comme ça on fait pour chaque service, les fichier de configuration vous les trouvez dans les dossier dédié pour chaque service  
helm install filebeat elastic/filebeat -f filebeat-values.yaml
helm install logstash elastic/logstash -f logstash-values.yaml
helm install kibana elastic/kibana -f kibana-values.yaml