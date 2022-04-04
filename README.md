# bdx-jug-java-operator
Source code of the talk Java Operator for JUG Bordeaux

# Déroulé de la démo
## 🎉 Init project
 - la branche `01-init-project` contient le résultat de cette étape
 - [installer / mettre](https://sdk.operatorframework.io/docs/installation/) à jour la dernière version du [Operator SDK](https://sdk.operatorframework.io/) (v1.18.1 au moment de l'écriture du readme)
 - créer le répertoire `bdx-jug-java-operator`
 - dans le répertoire `bdx-jug-java-operator`, scaffolding du projet avec Quarkus : `operator-sdk init --plugins quarkus --domain fr.wilda --project-name bdx-jug-java-operator`
 - l'arborescence générée est la suivante:
    ```bash
    .
    ├── LICENSE
    ├── Makefile
    ├── PROJECT
    ├── README.md
    ├── pom.xml
    ├── src
    │   └── main
    │       ├── java
    │       └── resources
    │           └── application.properties
    ```
 - vérification que cela compile : `mvn clean compile`
 - tester le lancement: `mvn quarkus:dev`:
    ```bash
      __  ____  __  _____   ___  __ ____  ______ 
      --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
      -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \   
      --\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
      2022-04-04 15:22:23,000 WARN  [io.fab.kub.cli.Config] (Quarkus Main Thread) Found multiple Kubernetes config files [[/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig.yml, /Users/sphilipp/dev/ovh/k8s/k8s-colima.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig-trillio.yml]], using the first one: [/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml]. If not desired file, please change it by doing `export KUBECONFIG=/path/to/kubeconfig` on Unix systems or `$Env:KUBECONFIG=/path/to/kubeconfig` on Windows.

      2022-04-04 15:22:23,073 WARN  [io.fab.kub.cli.Config] (Quarkus Main Thread) Found multiple Kubernetes config files [[/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig.yml, /Users/sphilipp/dev/ovh/k8s/k8s-colima.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig-trillio.yml]], using the first one: [/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml]. If not desired file, please change it by doing `export KUBECONFIG=/path/to/kubeconfig` on Unix systems or `$Env:KUBECONFIG=/path/to/kubeconfig` on Windows.
      2022-04-04 15:22:23,078 WARN  [io.fab.kub.cli.Config] (Quarkus Main Thread) Found multiple Kubernetes config files [[/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig.yml, /Users/sphilipp/dev/ovh/k8s/k8s-colima.yml, /Users/sphilipp/dev/ovh/k8s/kubeconfig-trillio.yml]], using the first one: [/Users/sphilipp/dev/ovh/k8s/kubeconfig-example2.yml]. If not desired file, please change it by doing `export KUBECONFIG=/path/to/kubeconfig` on Unix systems or `$Env:KUBECONFIG=/path/to/kubeconfig` on Windows.
      2022-04-04 15:22:23,278 INFO  [io.qua.ope.run.AppEventListener] (Quarkus Main Thread) Quarkus Java Operator SDK extension 3.0.4 (commit: da80246 on branch: da80246dd6b953c245fcad5a01487db81d55a1bc) built on Wed Mar 02 23:29:51 CET 2022
      2022-04-04 15:22:23,278 WARN  [io.qua.ope.run.AppEventListener] (Quarkus Main Thread) No Reconciler implementation was found so the Operator was not started.
      2022-04-04 15:22:23,328 INFO  [io.quarkus] (Quarkus Main Thread) bdx-jug-java-operator 0.0.1-SNAPSHOT on JVM (powered by Quarkus 2.7.3.Final) started in 2.129s. Listening on: http://localhost:8080
      2022-04-04 15:22:23,329 INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
      2022-04-04 15:22:23,329 INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cdi, kubernetes, kubernetes-client, micrometer, openshift-client, operator-sdk, smallrye-context-propagation, smallrye-health, vertx]
    ```