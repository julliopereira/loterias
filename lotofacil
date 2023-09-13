#!/usr/bin/env bash

# tornar executavel

vd="\033[32m"
vm="\033[31m"
am="\033[33m"
bk="\033[m"

numeros_sorteados=(01 03 04 05 06 07 10 11 14 18 19 20 23 24 25)
numeros_jogados="numeros_jogados_lotofacil.txt"


while IFS= read -r linha ; do
    coloridos=()
    count=0
    for sorteado in "${numeros_sorteados[@]}"; do
        for jogado in $(echo $linha); do
            if [ "$jogado" -eq "$sorteado" ]; then
                num=$(echo -e "$vd$sorteado $bk")
                let count++
                break
            else
                num=$(echo -e "$sorteado ")        
            fi
        done
        coloridos+="$num"

    done
    echo -e "${coloridos[@]}:\t acertou $count\t jogo= $linha"
    unset coloridos

done < "$numeros_jogados"

