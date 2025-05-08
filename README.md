Présentation des scripts de crawling

    sequential_crawl.py
    Ce script met en place un crawling séquentiel avec une session partagée, permettant de garder les cookies et autres données entre les requêtes. Il suit un déroulement précis :
    🔹 Lecture des URLs depuis un fichier Sitemap au format XML
    🔹 Lancement d’un navigateur headless pour optimiser les ressources
    🔹 Traitement des URLs une par une, avec génération d’un fichier Markdown par page visitée
    🔹 Gestion des échecs lors de la navigation (journalisation des erreurs)
    🔹 Fermeture propre du navigateur une fois le processus terminé

    ✅ Idéal pour les cas où un suivi linéaire et le maintien d’une session sont essentiels.

    parallel_craw.py
    Ce script permet un crawling en parallèle pour améliorer considérablement la vitesse d’exécution. Il suit une logique asynchrone :
    🔹 Extraction des URLs depuis un fichier Sitemap XML
    🔹 Initialisation d’un navigateur headless comme dans le script séquentiel
    🔹 Exécution concurrente de tâches de crawling via asyncio
    🔹 Pour chaque URL, création d’un fichier Markdown documentant son contenu
    🔹 Traitement indépendant des erreurs pour chaque tâche
    🔹 Le navigateur est automatiquement fermé grâce à l’instruction async with

    ✅ Recommandé pour le traitement massif et rapide de nombreuses pages.

    single_craw.py
    Version simplifiée et minimale, ce script est conçu pour le crawling d’une seule URL.
    🔹 Configuration légère
    🔹 Parfait pour les tests, les démos ou les cas isolés
    🔹 Génére également un fichier Markdown résumant le contenu de la page
