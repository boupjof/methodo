<head>
  <meta http-equiv="content-type" content="text/html; charset=utf-8" />
</head>
[index](index.html)

## Stegano

### Analyse basique 
-file filename (vérification type de fichier)
-strings filename (chaines en clair contenues... on peut imposer un nombre minimal de caractères)
-hachoir-metadata filename (il existe aussi d'autres exif tools)
-hachoir-subfile filename ==> détecte s'il y a des fichiers d'inclus/caché à l'intérieur

### Textes
- Début (lettre ou mot) de mot, début de ligne, début de phrase
- Tous les "n" lettres ou tous les "n" mots
- Conserver les majuscules
- Alphabet bilitère de Lord Bacon. Ex: 
- Espaces entre les mots (surtout sur du html -> regarder la source)

### Images 
- Zoomer chaque partie
- Est-ce un autostéréogramme ? (stegsolve peut aider à les lire)
- Jouer sur la luminosité et le contratse
- Jouer sur les seuils, filtrer
- Si c'est un gif, ouvrir avec gimp par exemple pour voir toutes les images de l'animation
- Si des bandes de 2 couleurs : traduire en binaire
- Regarder la palette de couleur
- Regarder les valeurs hexa de chaque couleur : conversion en ascii par exemple
- LSB, plans couleur (stegsolve, steganabara pour une première approche, sinon outil maison).
- Pour le LSB utiliser zsteg : "zsteg imagefile" et sinon "zsteg imagefile -o ALL"
- Si l'image contient un texte, regarder si certaines lettres (ou mots) ne sont pas marqués (auquel cas les conserver uniquement)
- Si c'est un png, regarder s'il n'y a pas des chunks inutilisés (qui contiendraient un autre fichier)
- Si c'est un bmp (par exemple), regarder si la taille de l'image correspond à ce qui est indiqué dans le header (x*y*nbc couleurs). Le header a p-e ete trafique pour masquer une partie de l'image

### Sons
- Regarder avec audacity pour séparer les canaux
- Sur le signal : crête = 1, creux = 0
- Inverser l'ordre, amplifier, ralentir le son
- Spectrogramme (avec outil sonic-visualiser par exemple) : visuellement cela peut afficher un mot
- Différence LSB entre 2 canaux
- Sous windows, il existe un (vieil) outil appelé MP3Stego

### Videos
- Regarder chaque frame

### Outils
- Steghide (date de 2003) : cache/extrait pour les formats JPEG, BMP, WAV and AU files
- OpenPuff (windows... non testé)