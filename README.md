# rendu3-2025
**Raffinement du diagramme de classes pour le système de réservation d'hôtel**

---

### Classe Utilisateur
```plaintext
Utilisateur
-------------
+ id : int (unique)
+ nom : string
+ email : string (unique, non null)
+ motDePasse : string (non null)
```

---

### Classe Client (hérite de Utilisateur)
```plaintext
Client : Utilisateur
-------------
+ listeReservations : List<Reservation>
```

---

### Classe Administrateur (hérite de Utilisateur)
```plaintext
Administrateur : Utilisateur
-------------
+ listeChambresGerees : List<Chambre>
```

---

### Classe Chambre
```plaintext
Chambre
-------------
+ numero : int (unique)
+ type : string  // Ex: Simple, Double, Suite
+ prix : float (>= 0)
+ etat : string  // Ex: Libre, Réservée, En nettoyage
```

---

### Classe Reservation
```plaintext
Reservation
-------------
+ id : int (unique)
+ dateDebut : Date
+ dateFin : Date
+ statut : string  // Ex: Confirmée, Annulée, En attente

+ client : Client
+ chambre : Chambre
```

---

### Contraintes supplémentaires :
- `dateDebut < dateFin`
- Une `Chambre` ne peut être concernée que par une seule réservation sur une période donnée.
- Un `Client` peut effectuer plusieurs réservations.
- Une `Chambre` est gérée par un seul `Administrateur`.


