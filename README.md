# Poisson-Image-Editing

# Projet de M1 : Étude et implémentation de l'édition d'images par équation de Poisson

Ce projet, réalisé dans le cadre du Master 1 MMAS de l'Université Paris Cité, présente une étude théorique et pratique de la technique de "Poisson Image Editing" pour la fusion avec rendu photoréaliste d'images. L'objectif est de comprendre, d'implémenter et de comparer deux méthodes numériques majeures pour la résolution de l'équation de Poisson.

## Aperçu du projet

L'édition de Poisson est une technique puissante qui permet d'insérer un objet d'une image source dans une image cible en préservant la cohérence des gradients. Cela permet d'obtenir une fusion "invisible", où l'éclairage et les couleurs de l'objet s'adaptent naturellement à la nouvelle scène, contrairement à un simple copier-coller.

Ce projet explore deux approches algorithmiques pour résoudre ce problème :
1.  **Méthode 1 :** Une approche par **différences finies** avec un solveur itératif de Jacobi.
2.  **Méthode 2 :** Une approche directe et performante utilisant la **transformée de Fourier rapide (FFT)**.

Le notebook `poisson_editing_project.ipynb` contient l'ensemble du code, des explications théoriques détaillées et l'analyse comparative des deux méthodes.

## Contenu du répertoire

-   `poisson_editing_project.ipynb`: Le notebook Jupyter principal contenant tout le projet.
-   `avion.jpg`: Image source.
-   `paysage.jpg`: Image cible.
-   `mask_avion.png`: Masque binaire délimitant la région à fusionner.
-   `README.md`: Ce fichier.

## Comment exécuter le projet

### Prérequis

Assurez-vous d'avoir Python 3 installé, ainsi que les bibliothèques suivantes. Vous pouvez les installer via pip :
```bash
pip install numpy opencv-python matplotlib
```

### Lancement

1.  Clonez ce dépôt ou téléchargez les fichiers dans un dossier local.
2.  Lancez Jupyter Notebook ou Google Colab depuis ce dossier :
    ```bash
    jupyter notebook
    ```
3.  Ouvrez le fichier `poisson_editing_project.ipynb`.
4.  Exécutez les cellules séquentiellement (`Cell > Run All`).

## Résultats attendus

Le notebook générera plusieurs visualisations, notamment :
-   La démonstration du défaut d'un collage naïf.
-   Le résultat de la fusion par la méthode de Jacobi.
-   Le résultat de la fusion par la méthode de Fourier.
-   Une figure de comparaison finale affichant les deux résultats côte à côte, avec leurs temps d'exécution respectifs.

L'analyse conclut à la supériorité de la méthode de Fourier en termes de performance, avec un facteur d'accélération mesuré d'environ **10x** sur l'exemple fourni.
