# Questions

Répondez ici aux questions théoriques en détaillant un maxium vos réponses :

1) Expliquer la procédure pour réserver un nom de domaine chez OVH avec des captures d'écran (arrêtez-vous au paiement) :
    1. Se rendre sur https://www.ovhcloud.com/fr/domains/
    2. Indiquer quel nom de domain on souhaite 
    3. Sélectioner l'extension souhaité si disponible 
    4. Choisir si on veut lié notre nom de domain à un hébergement web 
        1. Si on choisi de lier un hébergement web :
            -> On va devoir choisir le CMS / un CDN / Le certificat SSL que l'on souhaite / Si on veut une instance Web Cloud data base / Une amélioration DNS
    5. Accéder à la page de payment 

2. Comment faire pour qu'un nom de domaine pointe vers une adresse IP spécifique ?
    En général, dans l'interface de notre hebergeur, dans la gestion des paramètes de nom de domaine, on peut éditer un enregistrement pour notre nom de domaine avec et sans www., et faites-les pointer vers l'IP de votre serveur.
3. Comment mettre en place un certificat SSL ?
    Dans aaPanel, c'est tout simplement dans la partie website -> SSL -> Let's Encrypt. Après ca il suffit de choisir le nom de domain