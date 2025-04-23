
# Rapport Technique - Application E-commerce

**Auteur** : Ayoub Hlila
**Technologies utilisées** : Vue.js (Front-end), Spring Boot (Back-end), MySQL, Swagger, Postman

---

## Objectif du projet
Réalisation d’une application e-commerce complète pour le compte d’Alten, permettant :
- La gestion des produits
- L’ajout au panier et à la wishlist
- L’authentification via JWT
- Un formulaire de contact

---

## Partie Front-end (Vue.js)

### Architecture
src/
├── App.vue
├── main.js
├── router.js
├── assets/
├── components/
│   ├── ProductCard.vue
│   └── Navbar.vue
├── views/
│   ├── ShopView.vue
│   ├── CartView.vue
│   └── ContactView.vue
└── services/
    └── api.js

### Fonctionnalités développées
- Affichage dynamique des produits avec recherche et pagination
- Ajout au panier avec gestion des quantités
- Visualisation et modification du panier
- Formulaire de contact avec validation (email obligatoire, message < 300 caractères)
- Message de confirmation après envoi du message

---

## Partie Back-end (Spring Boot)

### Technologies et outils
- Spring Boot
- Spring Security + JWT
- JPA + Hibernate
- MySQL
- Swagger pour la documentation de l’API

### Endpoints disponibles
| Ressource        | Méthodes prises en charge                    |
|------------------|---------------------------------------------|
| /products        | GET, POST (admin), DELETE (admin), PATCH (admin) |
| /products/{id}   | GET, DELETE (admin), PATCH (admin)         |
| /account         | POST                                        |
| /token           | POST (authentification JWT)                 |
| /cart            | GET, POST, DELETE                           |
| /wishlist        | GET, POST, DELETE                           |

### Sécurité
- Authentification JWT
- Seul l’utilisateur `admin@admin.com` peut modifier les produits

### Modèle de données
class Product {
  Long id;
  String code;
  String name;
  String description;
  String image;
  String category;
  double price;
  int quantity;
  String internalReference;
  int shellId;
  String inventoryStatus;
  int rating;
  Timestamp createdAt;
  Timestamp updatedAt;
}

---

## Documentation Swagger
Accessible à l'adresse : `http://localhost:8080/swagger-ui/index.html`
- Présente l'ensemble des endpoints
- Permet de tester les requêtes avec authentification

---

## Tests Postman
Une collection Postman a été générée pour valider :
- La création d’un compte
- La connexion JWT
- La gestion des produits (CRUD)
- Le panier et la wishlist

---

## Stratégie de test

### Front-end
- **Tests manuels** : navigation, formulaire, pagination, ajout au panier
- **Validation DOM** : vérification du rendu conditionnel et des messages d’erreur

### Back-end
- **Tests unitaires** : services (ProductService, AuthService)
- **Tests d’intégration** : contrôleurs, base de données H2 en mémoire
- **Tests automatisés** via Swagger/Postman

---

## Statut du projet
✅ Toutes les fonctionnalités demandées dans le cahier des charges ont été implémentées :
- Gestion produits
- Authentification JWT
- Panier et wishlist
- Front Vue.js avec navigation, formulaire, pagination

### Bonus intégrés
- ✅ Filtrage par recherche produit
- ✅ Pagination
- ✅ Ajout de quantité personnalisée au panier
- ✅ Documentation Swagger
- ✅ Tests Postman

---

**Projet réalisé avec succès par Ayoub Hlila**
