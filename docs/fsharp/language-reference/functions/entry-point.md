---
title: Punto di ingresso
description: Informazioni su come impostare il punto di ingresso un F# programma che viene compilato come file eseguibile, in cui inizia formalmente l'esecuzione.
ms.date: 05/16/2016
ms.openlocfilehash: 915ab17b9a4fc7fd4d0ae344cb273b1d348a02f1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614349"
---
# <a name="entry-point"></a>Punto di ingresso

In questo argomento viene descritto il metodo utilizzato per impostare il punto di ingresso un F# programma.

## <a name="syntax"></a>Sintassi

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *associazione di funzione let* è la definizione di una funzione in un `let` associazione.

Il punto di ingresso a un programma che viene compilato come file eseguibile è dove formalmente inizia l'esecuzione. Si specifica il punto di ingresso per un F# applicazione applicando il `EntryPoint` dell'attributo del programma `main` (funzione). Questa funzione (creato tramite un `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato. L'ultimo file compilato è l'ultimo file nel progetto o l'ultimo file che viene passata alla riga di comando.

La funzione di punto di ingresso ha tipo `string array -> int`. Gli argomenti specificati nella riga di comando vengono passati al `main` funzione nella matrice di stringhe. Il primo elemento della matrice è il primo argomento. il nome del file eseguibile non è incluso nella matrice, come succede in altri linguaggi. Il valore restituito viene utilizzato come il codice di uscita del processo. Zero indica in genere eseguita correttamente. valori diversi da zero indicano un errore. Non sono previste convenzioni per il particolare significato dei codici restituiti diversi da zero; il significato dei codici restituiti è specifici dell'applicazione.

L'esempio seguente illustra un semplice `main` (funzione).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Quando viene eseguito questo codice con la riga di comando `EntryPoint.exe 1 2 3`, l'output è come indicato di seguito.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto di ingresso impliciti

Quando un programma non ha alcun **EntryPoint** attributo che indica in modo esplicito il punto di ingresso, le associazioni di livello superiore nell'ultimo file da compilare sono usati come punto di ingresso.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Associazioni let](let-bindings.md)