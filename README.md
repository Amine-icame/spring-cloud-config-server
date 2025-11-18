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
-   <img width="1237" height="862" alt="image" src="https://github.com/user-attachments/assets/92600798-d679-4918-9258-aaeb0a0cec21" />

-   `http://localhost:8888/microservice-produits/default`
-   <img width="1020" height="715" alt="image" src="https://github.com/user-attachments/assets/b573b4d2-8bb5-4d36-90c2-971aee330f94" />

-   `http://localhost:8888/spring-cloud-gateway/default`
-   <img width="1023" height="718" alt="image" src="https://github.com/user-attachments/assets/6307096d-f13d-43b5-8988-5277eb667193" />


Vous devriez voir les configurations correspondantes au format JSON.

---

*Développé par Amine içame/Salma benOmar pour le module JEE.*
