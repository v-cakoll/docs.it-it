---
title: Punto di ingresso
description: Informazioni su come impostare il punto di ingresso per F# un programma compilato come file eseguibile, in cui viene avviata formalmente l'esecuzione.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630528"
---
# <a name="entry-point"></a>Punto di ingresso

In questo argomento viene descritto il metodo utilizzato per impostare il punto di ingresso di F# un programma.

## <a name="syntax"></a>Sintassi

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *let-function-binding* è la definizione di una funzione in un' `let` associazione.

Il punto di ingresso di un programma compilato come file eseguibile è il punto in cui viene avviata formalmente l'esecuzione. È possibile specificare il punto di ingresso F# a un'applicazione applicando l' `EntryPoint` attributo `main` alla funzione del programma. Questa funzione (creata utilizzando un' `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato. L'ultimo file compilato è l'ultimo file del progetto o l'ultimo file passato alla riga di comando.

La funzione del punto di ingresso `string array -> int`è di tipo. Gli argomenti specificati nella riga di comando vengono passati alla `main` funzione nella matrice di stringhe. Il primo elemento della matrice è il primo argomento; il nome del file eseguibile non è incluso nella matrice, come in altri linguaggi. Il valore restituito viene usato come codice di uscita per il processo. Zero indica in genere esito positivo. i valori diversi da zero indicano un errore. Non esiste alcuna convenzione per il significato specifico di codici restituiti diversi da zero; i significati dei codici restituiti sono specifici dell'applicazione.

Nell'esempio seguente viene illustrata una `main` funzione semplice.

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

Quando questo codice viene eseguito con la riga `EntryPoint.exe 1 2 3`di comando, l'output è il seguente.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto di ingresso implicito

Quando un programma non dispone di un attributo **EntryPoint** che indica in modo esplicito il punto di ingresso, le associazioni di primo livello nell'ultimo file da compilare vengono utilizzate come punto di ingresso.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Associazioni let](let-bindings.md)
