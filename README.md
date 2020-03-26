# Data Analiste en Python
* Ce cours illustré à travers un exemple d'estimation de prix de voiture,
  dans ce cours, nous allons analyser nos données à travers le langage **Python**
  qui est l'un des langages incontournables dans le monde l'**AI (Intelligence Artificielle)**.

* et ensuite, nous allons introduire quelques **libraires de Python** utilisées dans le metier du
  **Data Analiste**

* en fin nous allons apprendre à importer et exporter des **données** et voici en quelques mot un
  bref résumé du cours.

## Objectifs
1. Répondre aux problèmes nécessitant une analyse des données
2. Analyser un jeu de données à  en Python
3. Présentation des librairies ou packages Python pour l'analyse des données
4. Comment importer et exporter des données en Python
5. Aperçu de base de l'ensemble de données

## Problème
 Est ce que pouvions-vous estimer le prix des voitures ?
* Pour répondre à cette question, nous allons utiliser différents packages 
  Python pour effectuer le nettoyage des données,
* analyse exploratoire des données, développement de modèles et évaluation de modèles. 

## Présentation de Quelques Libraires ou Package en Data Science en Python
Une bibliothèque Python est une collection de fonctions et de méthodes qui 
vous permettent d'effectuer beaucoup d'actions sans écrire de code.

Les bibliothèques contiennent généralement des modules intégrés 
offrant différentes fonctionnalités, qui vous pouvez utiliser directement.
Et il existe de vastes bibliothèques, offrant une large gamme d'installations.
Nous avons divisé les bibliothèques d'analyse de données Python en trois groupes:
le premier groupe est appelé 

### bibliothèques de calcul scientifique 
1. **Pandas** propose une structure de données et des outils pour manipulation et analyse 
efficaces des données.
Il fournit un axe rapide aux données structurées.
L'instrument principal de Pandas est un tableau à deux dimensions composé d'étiquettes de colonnes et de lignes, qui sont appelés **DataFrame**.
Il est conçu pour fournir une fonctionnalité d'indexation facile.
2. **La bibliothèque Numpy** utilise des tableaux pour ses entrées et sorties.
Il peut être étendu aux objets pour les matrices, et avec des changements
de codage mineurs, les développeurs peut effectuer un traitement de tableau rapide.
3. **SciPy** comprend des fonctions pour certains problèmes mathématiques avancés, comme indiqué sur cette diapositive, comme ainsi que la visualisation des données.
L'utilisation de méthodes de visualisation des données est le meilleur moyen de communiquer avec les autres, en leur montrant résultats d'analyse significatifs.

### Ces bibliothèques vous permettent de créer des graphiques, des graphiques et des cartes.
1. **Matplotlib** est la bibliothèque la plus connue pour la visualisation de données.
Il est idéal pour créer des graphiques et des tracés. Les graphiques sont également hautement personnalisables.
2. **Seaborn** est une autre bibliothèque de visualisation de haut niveau. Il est basé sur **Matplotlib.** Il est très facile de générer divers tracés tels que des **heat maps**, des **time series** et **violon**
parcelles.
Avec les algorithmes d'apprentissage automatique, nous sommes en mesure de développer un modèle en utilisant notre ensemble de données, et obtenir des prédictions.
Ouvrir dans Google Traduction	

### Les bibliothèques algorithmiques 
Les bibliothèques algorithmiques s'attaquent à certaines tâches d'apprentissage automatique du basique au complexe.
Nous présentons ici deux packages: 
* **La bibliothèque Scikit-learn** contient des outils pour modélisation statistique, y compris régression, classification, clustering, etc.
Cette bibliothèque est construite sur **NumPy**, **SciPy** et **Matplotlib**.
StatsModels est également un module Python qui permet aux utilisateurs d'explorer des données, d'estimer des statistiques
modèles et effectuer des tests statistiques.

## Leçon 2: Lecture de données en Python
Une fois que nous avons nos données en Python, nous pouvons effectuer toutes les procédures d'analyse de données suivantes nous avons besoin.
L'acquisition de données est un processus de chargement et de lecture de données dans un ordinateur portable à partir de diverses sources.
Pour lire des données à l'aide du package pandas de Python, il y a deux facteurs importants à considérer:
* format (csv, sql, json, xsl, ....)
* chemin du fichier d'accèss du fichier 

### Format:
Le format est la façon dont les données sont encodées.
Nous pouvons généralement indiquer différents schémas de codage en regardant la fin du nom de fichier.
Certains encodages courants sont: <code> csv, json, xlsx, hdf et ainsi de suite</code>.

### Chemin d'accèss:
Le chemin (du fichier) nous indique où les données sont stockées.
Habituellement, il est stocké sur l'ordinateur que nous utilisons ou en ligne sur Internet.

Dans notre cas, nous avons trouvé un ensemble de données de voitures d'occasion, qui a été obtenu à partir de l'adresse Web indiquée: 
<a href="https://archive.ics.uci.edu/autos/imports-85.data">https://archive.ics.uci.edu/autos/imports-85.data</a>

### CSV (comma separeted value)
Le format est **csv**, qui représente les valeurs séparées par des virgules, avace la bibliothèque
**pandas** de Python, nous pouvons lire les données avec la methode **read_csv(lien)**<br/>
  Ex: 
  <code>
  	<pre>
  		import pandas as pd
  		lien = "C:\Users\damaro\DataAnalysiswithPython\car.csv"
  		df = pd.read_csv(lien)
  	</pre>
  </code>
* nous ne voulons pas afficher les entêtes d'un fichier, il suffit d'utiliser la methode l'argument 
  **header** avec valeur **None** comme ceci:<br/> Ex: <code>df = pd.read_csv(lien, header=None)</code>

Après avoir lu le jeu de données, c'est une bonne idée de regarder le **dataframe** pour avoir une meilleure intuition et pour vous assurer que tout s'est déroulé comme prévu.
Étant donné que l'impression de l'ensemble de données peut prendre trop de temps et de ressources, pour gagner du temps,nous pouvons simplement utiliser:
* **dataframe.head ()** pour afficher les n premières lignes du bloc de données.<br/>
<code>
	<pre>
		df.head(n)
	</pre>
</code>
ou
pour les 5 premières lignes, on fait simplement:
<code>
	<pre>
		df.head(n)
	</pre>
</code>

* De même, dataframe.tail (n) affiche les n dernières lignes du bloc de données.
<code>
	<pre>
		df.tail(n)
	</pre>
</code>
ou
pour les 5 dernières lignes, on fait simplement:
<code>
	<pre>
		df.tail()
	</pre>
</code>

* Affecter un entête un à un dataframe au cas oû il n'ya pas d'entête
on va d'abord stocker les entête dans une list puis affecter ce tableau avec l'attribut 
**columns**
<code>
	<pre>
		headers = ['prix', 'category','duree', 'couleur','marque','model']
		df.columns = headers
	</pre>
</code>

### Exporter les données 
À un moment donné, après avoir effectué des opérations sur votre trame de données, vous souhaiterez peut-être
pour exporter votre base de données pandas vers un nouveau fichier **CSV**.
Vous pouvez le faire en utilisant la méthode "to_csv ()"
Pour ce faire, spécifiez le chemin d'accès au fichier (qui inclut le nom de fichier) dans lequel vous souhaitez écrire.
Par exemple, si vous souhaitez enregistrer le cadre de données **df** sous "automobile.csv" sur votre
propre ordinateur, vous pouvez utiliser la syntaxe: df.to_csv ("automobile.csv")<br/>
<code>
	<pre>
		url = "C:\Users\damaro\DataAnalysiswithPython\automobile.csv"
		df.to_csv(url)
	</pre>
</code>
Cependant, pandas prend également en charge l'importation et l'exportation de la plupart des types de fichiers de données avec différents<br/>

<table>
	<thead>
		<tr>
			<th>Format de données</th>
			<th>Lecture</th>
			<th>Ecriture</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>CSV</td>
			<td>pd.read_csv(lien)</td>
			<td>pd.to_csv(lien)</td>
		</tr>
		<tr>
			<td>JSON</td>
			<td>pd.read_json(lien)</td>
			<td>pd.to_json(lien)</td>
		</tr>
		<tr>
			<td>excel</td>
			<td>pd.read_excel(lien)</td>
			<td>pd.to_excel(lien)</td>
		</tr>
		<tr>
			<td>SQL</td>
			<td>pd.read_sql(lien)</td>
			<td>pd.to_sql(lien)</td>
		</tr>
	</tbody>
</table>
La syntaxe du code pour lire et enregistrer d'autres formats de données est très similaire à la lecture ou à l'enregistrement
fichier csv.
Chaque colonne montre une méthode différente pour lire et enregistrer des fichiers dans un format différent.