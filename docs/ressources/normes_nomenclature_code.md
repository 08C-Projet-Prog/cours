
# Nomenclature de Code  
<blockquote>D'après les notes de cours de Martin Vézina</blockquote>

Ce document présente les normes et conventions à respecter en matière de nomenclature du code. La science est plus directive que pour les commentaires, mais là encore, des choix communautaires ou culturels peuvent s’imposer.

---

### Variables

**Variables d’instance et transitoires** :
- Utilisez `camelCase` et la notation hongroise (ex. `notationDiteHongroise`).
- Pas d’articles (le, la, un, des), mais prépositions autorisées (en, pour, dans).
- Noms mnémotechniques : `sommeCarres`, `totalFacture`, `nomUtilisateur`.
- Préférez `hauteurEnMetres` à `hauteurMetres`.
- Abréviations acceptées si reconnues : `qteArticles`, `nbreCarte`.

**Variables transitoires** :
- Itérateurs : `i`, `c`, `ii`, `cc`.
- Tampons (échange de valeurs) : `temp`.

**Constantes** :
- Variables globales statiques et/ou finales :
  - Statiques : `NOMBRE_VISITES` (SCREAMING_CASE)
  - Finales : `PI`

**Attributs**
- Notation préfixée par `_` :
  - `_prenom`

**Propriétés**
- Noms communs avec une majuscule : `Voiture`, `MontantTotal`.


---

### Classes et Interfaces

- Noms communs avec une majuscule : `Voiture`, `CalculateurValeurVoiture`.
- Interfaces : préfixe `I` : `IPersonne`.

---

### Méthodes

- Verbes transitifs en notation hongroise.
- Majuscule ou minuscule selon le langage :
  - **C#** : `CalculerSurfacePolygone()`
  - **Java** : `calculerSurfacePolygone()`

---

### Conclusion

Les conventions de nomenclature doivent garantir :
- **Lisibilité**
- **Constance**
- **Uniformité** dans la communauté.
