---
title: Delegati (F#)
description: "Acquisire familiarità con i delegati in F #."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a>Delegati

Un delegato rappresenta una chiamata di funzione come oggetto. In F #, è in genere consigliabile utilizzare valori di funzione per rappresentare funzioni come valori di prima classe. Tuttavia, i delegati vengono utilizzati in .NET Framework e pertanto sono necessari quando si interagisce con le API che associno. Potrebbe inoltre essere utilizzati quando creazione di librerie progettate per utilizzare da altri linguaggi .NET Framework.


## <a name="syntax"></a>Sintassi

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Note
Nella sintassi precedente, `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito. I tipi di argomento che sono rappresentati da `type1` vengono automaticamente sottoposti a currying. Ne consegue che per questo tipo è utilizzare una forma di tupla se gli argomenti della funzione di destinazione vengono sottoposti a currying e una tupla tra parentesi per gli argomenti che sono già sotto forma di tupla. Currying automatico consente di rimuovere un set di parentesi, lasciando un argomento di tupla che corrisponda al metodo di destinazione. Vedere l'esempio di codice per la sintassi da utilizzare in ogni caso.

I delegati possono essere allegati a valori di funzione di F # e statici o metodi di istanza. I valori di funzione F # possono essere passati direttamente come argomenti per i costruttori di delegati. Per un metodo statico, il delegato viene costruito utilizzando il nome della classe e il metodo. Per un metodo di istanza, specificare l'istanza dell'oggetto e un metodo in un argomento. In entrambi i casi, operatore di accesso ai membri (`.`) viene utilizzato.

Il `Invoke` metodo nel tipo delegato chiama la funzione incapsulata. Inoltre, i delegati possono essere passati come valori di funzione facendo riferimento al nome di metodo Invoke senza le parentesi.

Il codice seguente viene illustrata la sintassi per la creazione di delegati che rappresentano i vari metodi in una classe. A seconda se il metodo è un metodo statico o un metodo di istanza e se questo dispone di argomenti nel formato tupla o sottoposte a currying, la sintassi per dichiarare e assegnare il delegato è leggermente diversa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Il codice seguente vengono illustrate alcune delle diverse modalità che l'utilizzo di delegati.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

L'output dell'esempio di codice precedente è come indicato di seguito.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Parametri e argomenti](parameters-and-arguments.md)

[Eventi](members/events.md)
