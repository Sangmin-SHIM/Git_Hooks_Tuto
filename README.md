# Git_Hooks_Tuto
EPSI B3 Cours

## Exercice 1
Créer un hook qui vous empêche de commit quoi que ce soit : `pre-commit`  <br>

> #!/bin/sh
>
> branch="$(git rev-parse --abbrev-ref HEAD)"
>
> if [ "$branch" = "main" ]; then
> 
>   echo "ALERT : Commit impossible sur la branche main"
>   
>   exit 1
>   
> fi


Créer un hook qui vérifie que votre message de commit commence bien par Bonjour : `commit-msg`  <br>

> #!/usr/bin/env bash
> 
> INPUT_FILE=$1
> 
> START_LINE=`head -n1 $INPUT_FILE`
> 
> PATTERN="^Bonjour"
> 
> if  [[ "$START_LINE" =~ $PATTERN ]]; then
> 
>   echo "Bad commit message, see example: Bonjour. [your commit messages]"
>   
>   exit 1
>   
> fi

Créer un hook qui vérifie que le nombre de caractères dans votre message de commit est pair. <br>
Créer un hook qui vérifie que votre message de commit commence bien au format “XXX-0000” ou les X sont des lettres et les 0 sont des chiffres

## Exercice 2
Créer un hook qui vous empêche de push. <br>
Créer un hook qui vérifie le nom de la destination quand vous tentez de push. Si ce dernier ne contient pas votre nom, rejeté le push <br>
Créer un hook qui vous dit bonjour à chaqu
