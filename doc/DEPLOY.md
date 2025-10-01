# Procédure de Déploiement

Décrivez ci-dessous votre procédure de déploiement en détaillant chacune des étapes. De la préparation du VPS à la méthodologie de déploiement continu.

## Préparation du VPS

Pour la préparation du VPS, même si non fonctionnel actuellement, on m'a fourni 
un domaine / adresse IP / Indentifiant SSH / mot de passe ssh 

1. ping le serveur fournis 
2. Se connecter en ssh debian@$IP
3. Installer aaPanel : URL=https://www.aapanel.com/script/install_7.0_en.sh && if [ -f /usr/bin/curl ];then curl -ksSO "$URL" ;else wget --no-check-certificate -O install_7.0_en.sh "$URL";fi;bash install_7.0_en.sh aapanel
4. Accéder à aaPanel et faire la création LMNP 
5. Créer le site avec une BDD
6. Créer le dépôt git bare avec : 
    1. mkdir -p /var/repo/$SERVEUR.git 
    2. cd /var/repo/$SERVEUR.git
    3. /var/repo/$SERVEUR.git# git init --bare
7. Créer le hook de déploiement 
    1. nano hooks/post-receive 
       TARGET="/www/wwwroot/$SERVEUR"
       GIT_DIR="/var/repo/$SERVEUR.git"
       git --work-tree=$TARGET --git-dir=$GIT_DIR checkout -f master
       chown -R www:www $TARGET
    2. chmod +x hooks/post-receive
8. Depuis le local faire : git remote add production ssh://root@$IP/var/repo/$SERVEUR.git
9. git push production main:master 
10. Sur aapnel, allez dans « website » , « conf » de notre website, site directory -> running directory et mettre /public 
    et la actuellement je n'ai pas de /public 


## Méthode de déploiement

Todo...
