# Concorsi On-Line Stazione Zoologica Anton Dohrn

## Requisiti

Per l'avvio in locale occorre una istanza di [Alfresco Community Edition](https://www.alfresco.com/thank-you/thank-you-downloading-alfresco-community-edition) attiva sulla porta 9080, la versione minima è la 5.0.1 Community.  

Successivamente applicare i seguenti amps:
- https://repo.maven.apache.org/maven2/it/cnr/si/alfresco/groups-extension/2.22/groups-extension-2.22.amp
- https://repo.maven.apache.org/maven2/it/cnr/si/alfresco/zip-content/2.22/zip-content-2.22.amp
- https://repo.maven.apache.org/maven2/it/cnr/si/alfresco/cnr-extension-content-model/2.22/cnr-extension-content-model-2.22.amp

**Per una corretta inizializzazione delle risorse installare Alfresco localizzato in Inglese**

### Docker Alfresco
In alternativa si può rendere disponibile Alfresco tramite [docker-compose](docker-compose/docker-compose.yml)   
```bash
git clone https://github.com/consiglionazionaledellericerche/cool-jconon-szn.git
cd cool-jconon-szn/docker-compose
docker-compose up -d
```

## Compilazione e Primo Avvio

```bash
git clone https://github.com/consiglionazionaledellericerche/cool-jconon-szn.git
cd cool-jconon-szn
mvn clean install -Pprod
java -jar target/selezioni-szn.war --user.admin.password=admin --server.servlet.context-path=/ --repository.base.url=http://localhost:9080/alfresco/ --spring.profiles.active=dev --spid.enable=true --spid.issuer.entityid=https://miauri.it --spid.destination=http://localhost:8080/spid/send-response
```

## Avvio locale

```bash
git clone https://github.com/consiglionazionaledellericerche/cool-jconon-szn.git
cd cool-jconon-szn
mvn clean spring-boot:run -Pprod -Dspring.profiles.active=dev -Dserver.servlet.context-path=/ -Duser.admin.password=admin -Drepository.base.url=http://localhost:9080/alfresco/
```

L'applicazionre sarà attiva alla seguente URL: <http://localhost:8080>

