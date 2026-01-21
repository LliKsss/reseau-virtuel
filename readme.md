Architecture à 3 niveaux :
-  LoadBalancer (HAProxy) - Point d'entrée sur le port 9090, route le trafic vers le firewall
-  Firewall (Wallarm) - Valide chaque requête selon le schéma OpenAPI, bloque les requêtes non conformes, transmet les valides au webserver
-  Webserver (Nginx) - Serveur web qui héberge votre application/contenu
-- Flux : Client → HAProxy:9090 → Firewall:8080 → Nginx:80 → réponse

Docker :
-  Utilisation du docker-compose.yml proposé dans le TP
-  Problème : conteneur firewall ne se lance pas
-  Modification du .yml
-  Ajout de 3 fichiers de configuration
-  Les 3 conteneurs sont bien lancé
Vous pouvez voir les preuves de la bonne éxécution des conteneurs dans docker-ps.png
Les fichiers contenant les résultats des logs et des curl sont aussi dispoible logs-result.txt & curl-result.txt
