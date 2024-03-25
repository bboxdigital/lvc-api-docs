**Documentation de l'API pour l'Upload de Fichiers CSV [BROUILLON]**

**Introduction:**
Cet API permet à nos partenaires d'uploader des fichiers CSV qui seront importés et consolidés avec les données de La Vitrine. 

**URL de base de l'API:** 
https://URL_API

---

**Endpoint d'Upload:**

- **URL:** `/v1/csv_upload`
- **Méthode:** `POST`
- **Description:** Cet endpoint permet d'uploader un fichier CSV.

**Paramètres:**

- `file` (obligatoire): Le fichier CSV que vous souhaitez uploader.
- `type` (obligatoire): Le type associé au fichier. Les valeurs possibles sont: "additionalTypes", "contributions", "contributors", "eventOffers", "events", "eventSeries", "exhibitionEvents", "images", "places".

**Réponses:**

- `200 OK`: Upload réussi.
  - Exemple de réponse:
    ```json
    {
        "status": "success",
        "path": "[nom_partenaire]/events/1234567890.csv"
    }
    ```
- `400 Bad Request`: Il y a eu un problème avec votre demande, comme un type de fichier incorrect ou un schéma invalide.
  - Exemple de réponse pour un fichier non-CSV:
    ```json
    {
        "error": "Seuls les fichiers CSV sont autorisés"
    }
    ```
  - Exemple de réponse pour un schéma invalide:
    ```json
    {
        "error": "Valeur de schéma invalide"
    }
    ```

---

**Authentification:**

Pour utiliser cette API, vous devez inclure votre clé API dans l'en-tête de chaque demande :

```
Authorization: Bearer VOTRE_CLÉ_API
```

Remplacez `VOTRE_CLÉ_API` par la clé API que nous vous avons fournie.

---

**Exemple d'Utilisation avec cURL:**

```bash
curl -X POST \
     -H "Authorization: Bearer VOTRE_CLÉ_API" \
     -F "file=@chemin_vers_votre_fichier.csv" \
     -F "type=events" \
     https://URL_API/v1/csv_upload
```

Remplacez `VOTRE_CLÉ_API` par votre clé API et `chemin_vers_votre_fichier.csv` par le chemin vers votre fichier CSV.

