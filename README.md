#!/bin/bash 
# my-first-repo


# Funktion zur Durchführung einer bestimmten Operation
function berechne {
  local zahl1=$1
  local zahl2=$2
  local operation=$3

  case "$operation" in
    +)
      echo "Die Summe ist: $((zahl1 + zahl2))"
      ;;
    -)
      echo "Die Differenz ist: $((zahl1 - zahl2))"
      ;;
    \*)
      echo "Das Produkt ist: $((zahl1 * zahl2))"
      ;;
    /)
      if [ $zahl2 -ne 0 ]; then
        echo "Der Quotient ist: $((zahl1 / zahl2))"
      else
        echo "Division durch Null ist nicht möglich!"
      fi
      ;;
    *)
      echo "Ungültige Operation!"
      ;;
  esac
}

# Benutzeraufforderung zur Eingabe der Zahlen und Operation
read -p "Gib die erste Zahl ein: " zahl1
read -p "Gib die zweite Zahl ein: " zahl2
read -p "Welche Operation soll durchgeführt werden (+, -, *, /)? " operation

# Aufruf der Berechnungsfunktion
berechne "$zahl1" "$zahl2" "$operation"

