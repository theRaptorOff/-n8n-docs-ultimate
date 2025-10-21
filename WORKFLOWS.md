# Documentation complète des Workflows n8n

## Introduction
n8n est un outil d'automatisation low-code permettant de créer des **workflows**.  
Un workflow est une suite de **nœuds** (nodes) reliés entre eux :  
- un **déclencheur** (trigger) lance le workflow,  
- des **nœuds intermédiaires** transforment les données,  
- un ou plusieurs **nœuds de sortie** exécutent une action.

---

# Core Nodes

## Cron
- **Rôle** : Déclenche un workflow à une heure précise ou à intervalle régulier.
- **Exemple** : exécuter un workflow tous les jours à 8h.

## Function
- **Rôle** : Permet d’écrire du code JavaScript personnalisé.
- **Exemple** :
```js
return [{ json: { total: items[0].json.price * 1.2 } }];
```

## Webhook
- **Rôle** : Déclenche un workflow lorsqu’une requête HTTP est reçue.
- **Exemple** : recevoir des données d’un formulaire web.

## HTTP Request
- **Rôle** : Appeler une API externe ou un service web.

## Email (Send/Receive)
- **Rôle** : Envoyer ou recevoir des emails.

## Merge
- **Rôle** : Combiner ou comparer deux flux de données.

## IF
- **Rôle** : Ajouter une condition (si / sinon).

## Switch
- **Rôle** : Rediriger le flux selon une valeur.

## Set / Edit Fields
- **Rôle** : Modifier ou créer de nouveaux champs.

---

# App Nodes populaires

## Google Sheets
- Lire et écrire des données dans des feuilles Google.

## Google Docs
- Créer et modifier des documents automatiquement.

## Slack
- Envoyer des messages dans Slack.

## Trello
- Créer ou mettre à jour des cartes.

## GitHub
- Interagir avec dépôts et issues.

## Stripe
- Gérer les paiements.

## Airtable
- Lire/écrire dans une base no-code.

## Notion / Asana / Discord / Mailchimp
- Divers outils collaboratifs et marketing.

---

# Exemples de Workflows types

### Workflow : Webhook → Slack
1. Formulaire web → POST request.
2. **Webhook** reçoit les données.
3. **Slack** envoie un message.

### Workflow : Cron → Google Sheets → Email
1. **Cron** déclenche chaque jour à 9h.
2. **Google Sheets** lit les ventes de la veille.
3. **Email** envoie un rapport.

### Workflow : Stripe → Airtable → Email
1. **Stripe** capte un paiement.
2. **Airtable** enregistre la donnée.
3. **Email** envoie une confirmation.

### Workflow : Webhook → OpenAI → Slack
1. **Webhook** reçoit une question.
2. **OpenAI** génère une réponse.
3. **Slack** poste la réponse.

---

# Bonnes pratiques
- Nommer clairement les nœuds.
- Tester avec de petits jeux de données.
- Utiliser IF / Switch pour garder le workflow lisible.
- Sauvegarder régulièrement les workflows.
- Gérer les erreurs via branches alternatives.
