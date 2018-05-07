---
title: Punto di ingresso (F#)
description: "Informazioni su come impostare il punto di ingresso per un programma F # che viene compilato come file eseguibile, in cui inizia formalmente l'esecuzione."
ms.date: 05/16/2016
ms.openlocfilehash: 3d6cab755dd89f2d3d669a8763aa08660432a0ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="entry-point"></a>Punto di ingresso

In questo argomento viene descritto il metodo utilizzato per impostare il punto di ingresso per un programma F #.


## <a name="syntax"></a>Sintassi

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Note
Nella sintassi precedente, *consentono di associazione di funzione* è la definizione di una funzione in un `let` associazione.

Il punto di ingresso a un programma che viene compilato come file eseguibile in cui inizia formalmente l'esecuzione. È possibile specificare il punto di ingresso a un'applicazione di F # applicando il `EntryPoint` attributo per il programma `main` (funzione). Questa funzione (creato tramite un `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato. L'ultimo file compilato è l'ultimo file nel progetto o l'ultimo file che viene passato alla riga di comando.

La funzione di punto di ingresso è di tipo `string array -> int`. Gli argomenti specificati nella riga di comando vengono passati per la `main` funzione nella matrice di stringhe. Il primo elemento della matrice è il primo argomento. il nome del file eseguibile non è incluso nella matrice, come in altri linguaggi. Il valore restituito viene utilizzato come il codice di uscita per il processo. Zero indica in genere eseguita correttamente. valori diversi da zero indicano un errore. Non sono previste convenzioni per il particolare significato del codice restituito diverso da zero; il significato dei codici restituiti è specifici dell'applicazione.

Nell'esempio seguente viene illustrato un semplice `main` (funzione).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Quando si esegue questo codice con la riga di comando `EntryPoint.exe 1 2 3`, l'output è come indicato di seguito.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto di ingresso implicito
Quando un programma non ha alcun **EntryPoint** attributo che indica in modo esplicito il punto di ingresso, le associazioni di livello superiore nell'ultimo file da compilare vengono utilizzati come punto di ingresso.


## <a name="see-also"></a>Vedere anche
[Funzioni](index.md)

[Associazioni let](let-bindings.md)
