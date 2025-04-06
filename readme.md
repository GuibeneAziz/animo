### Structure principale :  
| Entité                | Description                                  |
|-----------------------|---------------------------------------------|
| `Produit` (abstrait)  | Super-classe pour `Nourriture`/`Accessoire` |
| `Animal` (abstrait)   | Super-classe pour `AnimalTerrestre`/`AnimalVolant`/`AnimalAquatique` |
| `Personne`            | Classe parente pour `Client`/`Livreur`/`Admin` |
| `Commande`            | Contient panier + infos client              |

**Fonctionnalités clés** :  
- Gestion des stocks  
- Système de panier  
- Mécanisme de paiement  

---

## 3. Fonctionnalités détaillées par acteur  

### 🔹 Client  
- ✅ Consulter animaux (tri par type)  
- ✅ Consulter produits (nourriture/accessoires)  
- ✅ Ajouter articles au panier  
- ✅ Visualiser panier  
- ✅ Paiement (espèces/carte)  
- ✅ Saisie coordonnées  
- ✅ Génération commande après paiement  

### 🔹 Livreur  
- 🔐 Connexion (identifiant/mot de passe)  
- 📋 Affichage commandes  
- ✏️ Changer statut commande (`Acceptée`/`Livrée`)  
- 🗑️ Supprimer commande livrée  
- 🔒 Déconnexion  

### 🔹 Admin  
- 🔐 Connexion (identifiant admin)  
- ➕ Ajouter/modifier/supprimer animaux/produits  
- 📊 Afficher état du stock  
- 👥 Gestion utilisateurs (extension future)  

---

## 4. Cas d'utilisation  

### Cas 1 : Paiement de commande (Client)  
**Préconditions** :  
1. Panier non vide  
2. Client authentifié  
3. Informations personnelles valides  

**Postconditions** :  
1. Commande enregistrée  
2. Stock mis à jour  
3. Paiement validé  

**Table de décision** :  
| Panier non vide | Authentifié | Infos valides | Résultat  |
|-----------------|-------------|---------------|-----------|
| Vrai           | Vrai        | Vrai          | ✅ Succès |
| Vrai           | Faux        | Vrai          | ❌ Échec  |
| Faux           | Vrai        | Vrai          | ❌ Échec  |
| Vrai           | Vrai        | Faux          | ❌ Échec  |

---

### Cas 2 : Acceptation commande (Livreur)  
**Préconditions** :  
1. Livreur authentifié  
2. Commande disponible (non acceptée)  

**Postconditions** :  
1. Statut → "Acceptée"  
2. Assignée au livreur  

**Table de décision** :  
| Authentifié | Commande dispo | Résultat  |
|-------------|----------------|-----------|
| Vrai        | Vrai           | ✅ Succès |
| Vrai        | Faux           | ❌ Échec  |
| Faux        | Vrai           | ❌ Échec  |

---

## 5. Affichages & Interactions  
- 🖥️ Menus textuels dynamiques  
- 📜 Listes détaillées (animaux/produits)  
- 🔒 Saisie sécurisée des IDs  
- ✔️ Confirmations d'actions  
- 📦 Affichage structuré des commandes  

---**
### 6. Diagramme de cas d'utilisation
![Cas d'utilisation](.\classe.png)