---
title: Operatori aritmetici (F#)
description: 'Scopri gli operatori aritmetici sono disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 04/04/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 75ddcfa3-564e-4382-80a3-f9da73d0f0ea
ms.openlocfilehash: 8f11e77457bed40cff081a73181689610871e654
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="arithmetic-operators"></a>Operatori aritmetici

Questo argomento descrive gli operatori aritmetici che sono disponibili nel linguaggio F #.

## <a name="summary-of-binary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici binari
Nella tabella seguente sono riepilogati gli operatori aritmetici binari che sono disponibili per tipi a virgola mobile e integrali unboxed.

|Operatore binario|Note|
|---------------|-----|
|`+` (aggiunta, oltre a)|Non è selezionata. Possibile condizione di overflow quando vengono sommati numeri e la somma supera il valore assoluto massimo supportato dal tipo.|
|`-` (sottrazione, meno)|Non è selezionata. Quando vengono sottratti tipi senza segno o valori a virgola mobile sono troppo piccoli per essere rappresentato dal tipo di condizione possibili underflow.|
|`*` (moltiplicazione, ore)|Non è selezionata. Possibile condizione di overflow quando i numeri vengono moltiplicati e il prodotto supera il valore assoluto massimo supportato dal tipo.|
|`/` (divisione, divisa per)|Divisione per zero causa un <xref:System.DivideByZeroException> per i tipi integrali. Per tipi a virgola mobile, divisione per zero consente i valori a virgola mobile speciali `+Infinity` o `-Infinity`. È inoltre disponibile una condizione di possibili underflow quando un numero a virgola mobile è troppo piccolo per essere rappresentato dal tipo.|
|`%` (resto, rem)|Restituisce il resto di un'operazione di divisione. Il segno del risultato è uguale a quello del primo operando.|
|`**` (elevamento a potenza)|Possibile condizione di overflow quando il risultato supera il valore assoluto massimo per il tipo.<br /><br />L'operatore di elevamento a potenza funziona solo con tipi a virgola mobile.|

## <a name="summary-of-unary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici unari
Nella tabella seguente sono riepilogati gli operatori aritmetici unari disponibili per tipi a virgola mobile e integrali.


|Operatore unario|Note|
|--------------|-----|
|`+` (positivo)|Può essere applicato a qualsiasi espressione aritmetica. Non modifica il segno del valore.|
|`-` (negazione, negativo)|Può essere applicato a qualsiasi espressione aritmetica. Modifica il segno del valore.|
Il comportamento di overflow o underflow per i tipi integrali è a capo. In questo modo un risultato non corretto. Overflow di integer è un problema potenzialmente grave che può comportare problemi di sicurezza quando software non viene scritto in modo da poterlo gestire. Se si tratta di un problema per l'applicazione, è consigliabile utilizzare gli operatori selezionati in `Microsoft.FSharp.Core.Operators.Checked`.


## <a name="summary-of-binary-comparison-operators"></a>Riepilogo degli operatori di confronto binario
La tabella seguente illustra gli operatori di confronto binarie che sono disponibili per tipi a virgola mobile e integrali. Questi operatori restituiscono valori di tipo `bool`.

Poiché la rappresentazione a virgola mobile IEEE non supporta un'operazione di uguaglianza esatta, numeri a virgola mobile non devono essere confrontati per verificarne l'uguaglianza, mai direttamente. Due numeri che è possibile verificare facilmente sarà uguale controllando il codice potrebbero avere rappresentazioni in bit diverse.



|Operatore|Note|
|--------|-----|
|`=` (uguaglianza, uguale a)|Non è un operatore di assegnazione. Viene utilizzato solo per il confronto. Si tratta di un operatore generico.|
|`>` (maggiore di)|Si tratta di un operatore generico.|
|`<` (minore di)|Si tratta di un operatore generico.|
|`>=` (maggiore o uguale a)|Si tratta di un operatore generico.|
|`<=` (minore o uguale a)|Si tratta di un operatore generico.|
|`<>` (non uguale)|Si tratta di un operatore generico.|

## <a name="overloaded-and-generic-operators"></a>Operatori di overload e generici
Tutti gli operatori descritti in questo argomento sono inclusi il **FSharp** dello spazio dei nomi. Alcuni degli operatori vengono definiti utilizzando i parametri di tipo risolti staticamente. Ciò significa che sono presenti definizioni singoli per ogni tipo specifico che funziona con tale operatore. Tutti gli unario e binari operatori aritmetici e bit per bit sono in questa categoria. Gli operatori di confronto sono generici e pertanto funzionano con qualsiasi tipo, i tipi aritmetici non appena primitivi. Unione discriminata e tipi di record sono implementazioni personalizzate generate dal compilatore F #. Tipi di classe utilizzano il metodo <xref:System.Object.Equals%2A>.

Gli operatori generici sono personalizzabili. Per personalizzare le funzioni di confronto, eseguire l'override <xref:System.Object.Equals%2A> per fornire il confronto di uguaglianza personalizzato e quindi implementare <xref:System.IComparable>. Il <xref:System.IComparable?displayProperty=nameWithType> interfaccia dispone di un singolo metodo, il <xref:System.IComparable.CompareTo%2A> metodo.


## <a name="operators-and-type-inference"></a>Gli operatori e l'inferenza del tipo
L'utilizzo di un operatore in un'espressione vincola l'inferenza del tipo per tale operatore. Inoltre, l'utilizzo degli operatori impedisce generalizzazione automatica, in quanto l'utilizzo degli operatori implica un tipo aritmetico. In assenza di qualsiasi altra informazione, il compilatore F # deduce `int` come tipo di espressioni aritmetiche. È possibile eseguire l'override di questo comportamento specificando un altro tipo. In questo modo i tipi di argomento e tipo restituito di `function1` nel codice seguente vengono considerati `int`, ma i tipi per `function2` vengono considerati `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per simboli e operatori](index.md)

[Overload degli operatori](../operator-overloading.md)

[Operatori bit per bit](bitwise-operators.md)

[Operatori booleani](boolean-operators.md)
