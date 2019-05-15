---
title: Operatori aritmetici
description: Scopri gli operatori aritmetici che sono disponibili in di F# linguaggio di programmazione.
ms.date: 04/04/2018
ms.openlocfilehash: 74ab813a7ca5018b6bd084aea10627e4afd62015
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641651"
---
# <a name="arithmetic-operators"></a>Operatori aritmetici

In questo argomento descrive gli operatori aritmetici che sono disponibili in di F# linguaggio.

## <a name="summary-of-binary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici binari

Nella tabella seguente sono riepilogati gli operatori aritmetici binari che sono disponibili per tipi a virgola mobile e integrali unboxed.

|Operatore binario|Note|
|---------------|-----|
|`+` (addizione, oltre a)|Unchecked. Condizione di overflow possibili quando vengono sommati i numeri e la somma supera il valore assoluto massimo supportato dal tipo.|
|`-` (sottrazione meno)|Unchecked. Possibili underflow condizione quando vengono sottratti tipi senza segno o quando sono troppo piccoli per essere rappresentato dal tipo di valori a virgola mobile.|
|`*` (moltiplicazione, tempi)|Unchecked. Condizione di overflow possibili quando i numeri vengono moltiplicati e il prodotto supera il valore assoluto massimo supportato dal tipo.|
|`/` (divisione, divisa per)|Divisione per zero causa un <xref:System.DivideByZeroException> per i tipi integrali. Per i tipi a virgola mobile, divisione per zero consente i valori a virgola mobile speciali `+Infinity` o `-Infinity`. È inoltre disponibile una condizione di possibili underflow quando un numero a virgola mobile è troppo piccolo per essere rappresentato dal tipo.|
|`%` (parte rimanente, rem)|Restituisce il resto di un'operazione di divisione. Il segno del risultato è uguale a quello del primo operando.|
|`**` (l'elevamento a potenza, alla potenza di)|Possibile condizione di overflow quando il risultato supera il valore massimo assoluto per il tipo.<br /><br />L'operatore di elevamento a potenza funziona solo con tipi a virgola mobile.|

## <a name="summary-of-unary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici unari

Nella tabella seguente sono riepilogati gli operatori aritmetici unari che sono disponibili per i tipi integrali e a virgola mobile.

|Operatore unario|Note|
|--------------|-----|
|`+` (positivo)|Può essere applicato a qualsiasi espressione aritmetica. Non modifica il segno del valore.|
|`-` (negazione, negativa)|Può essere applicato a qualsiasi espressione aritmetica. Modifica il segno del valore.|

Il comportamento in caso di overflow o underflow per i tipi integrali prevede il wrapping. In questo modo un risultato errato. Overflow numero intero rappresenta un problema potenzialmente grave che può contribuire a problemi di sicurezza quando software non viene scritto in modo da poterlo gestire. Se si tratta di un problema per l'applicazione, è consigliabile usare gli operatori di selezionati `Microsoft.FSharp.Core.Operators.Checked`.

## <a name="summary-of-binary-comparison-operators"></a>Riepilogo degli operatori di confronto binarie

La tabella seguente illustra gli operatori di confronto binarie che sono disponibili per i tipi integrali e a virgola mobile. Questi operatori restituiscono valori di tipo `bool`.

Numeri a virgola mobile non devono essere mai confrontati direttamente per verificarne l'uguaglianza, poiché la rappresentazione a virgola mobile IEEE non supporta un'operazione di uguaglianza esatta. Due numeri che è possibile verificare facilmente sarà uguale esaminando il codice potrebbero avere rappresentazioni in bit diverse.

|Operatore|Note|
|--------|-----|
|`=` (uguaglianza, uguale a)|Questo non è un operatore di assegnazione. Viene utilizzato solo per il confronto. Si tratta di un operatore generico.|
|`>` (maggiore di)|Si tratta di un operatore generico.|
|`<` (minore di)|Si tratta di un operatore generico.|
|`>=` (maggiore o uguale a)|Si tratta di un operatore generico.|
|`<=` (minore o uguale a)|Si tratta di un operatore generico.|
|`<>` (non uguale)|Si tratta di un operatore generico.|

## <a name="overloaded-and-generic-operators"></a>Operatori di overload e generici

Tutti gli operatori descritti in questo argomento vengono definiti nel **FSharp** dello spazio dei nomi. Gli operatori di vengono definiti tramite i parametri di tipo risolti staticamente. Ciò significa che sono presenti definizioni singoli per ogni tipo specifico che funziona con tale operatore. Tutti gli unario e binari operatori aritmetici e bit per bit sono in questa categoria. Gli operatori di confronto sono generici e di conseguenza funzionano con qualsiasi tipo, non appena aritmetici tipi primitivi. Unione discriminata e tipi di record hanno le proprie implementazioni personalizzate che vengono generate dal F# compilatore. Tipi di classe usano il metodo <xref:System.Object.Equals%2A>.

Gli operatori generici sono personalizzabili. Per personalizzare le funzioni di confronto, eseguire l'override <xref:System.Object.Equals%2A> per fornire il proprio confronto di uguaglianza personalizzati e quindi implementare <xref:System.IComparable>. Il <xref:System.IComparable?displayProperty=nameWithType> interfaccia dispone di un singolo metodo, il <xref:System.IComparable.CompareTo%2A> (metodo).

## <a name="operators-and-type-inference"></a>Gli operatori e l'inferenza del tipo

L'uso di un operatore in un'espressione vincola l'inferenza del tipo in tale operatore. Inoltre, l'utilizzo degli operatori impedisce la generalizzazione automatica, in quanto l'utilizzo degli operatori implica un tipo aritmetico. In assenza di qualsiasi altra informazione, il F# viene dedotto dal compilatore `int` come tipo di espressioni aritmetiche. È possibile eseguire l'override di questo comportamento specificando un altro tipo. In questo modo i tipi di argomento e tipo restituito `function1` nel codice seguente vengono considerati `int`, ma i tipi per `function2` vengono considerati `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per simboli e operatori](index.md)
- [Overload degli operatori](../operator-overloading.md)
- [Operatori bit per bit](bitwise-operators.md)
- [Operatori booleani](boolean-operators.md)
