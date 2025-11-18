# Spring Cloud Config Server

Ce projet implémente le serveur de configuration centralisé de notre architecture de microservices. Il est responsable de la distribution des configurations aux microservices clients à partir d'un dépôt Git distant.

## 🚀 Technologies Utilisées

-   **Spring Boot 3+**
-   **Spring Cloud Config Server**
-   **Maven**
-   **Java 17+**
-   **GitHub** (pour le dépôt des configurations)

## ⚙️ Comment le Lancer ?

1.  **Prérequis :** Assurez-vous d'avoir cloné le dépôt de configuration (`microservices-config-repo`) et qu'il est accessible.
2.  **Configuration :**
    -   Modifiez `src/main/resources/application.properties` pour pointer vers l'URL de votre dépôt de configuration :
        ```properties
        server.port=8888
        spring.cloud.config.server.git.uri=https://github.com/votre_nom_utilisateur/microservices-config-repo.git
        # Si votre dépôt est privé, décommentez et configurez :
        # spring.cloud.config.server.git.username=votre_utilisateur_github
        # spring.cloud.config.server.git.password=votre_jeton_personnel
        ```
3.  **Lancement :**
    ```bash
    mvn spring-boot:run
    ```
    Le serveur sera accessible sur `http://localhost:8888`.

## 🧪 Vérification

Après le démarrage, vous pouvez vérifier que le serveur lit les configurations de votre dépôt Git en accédant à :
-   `http://localhost:8888/microservice-commandes/default`
-   `http://localhost:8888/microservice-produits/default`
-   `http://localhost:8888/spring-cloud-gateway/default`

Vous devriez voir les configurations correspondantes au format JSON.

---

*Développé par [Amine içame/Salma benOmar] pour le module JEE.*
