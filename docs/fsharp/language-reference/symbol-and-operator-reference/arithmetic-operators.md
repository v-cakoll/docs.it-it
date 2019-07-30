---
title: Operatori aritmetici
description: Informazioni sugli operatori aritmetici disponibili nel linguaggio di F# programmazione.
ms.date: 04/04/2018
ms.openlocfilehash: b783a0134541f11f06dde83af97676699b797da1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630787"
---
# <a name="arithmetic-operators"></a>Operatori aritmetici

In questo argomento vengono descritti gli operatori aritmetici disponibili F# nel linguaggio.

## <a name="summary-of-binary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici binari

Nella tabella seguente sono riepilogati gli operatori aritmetici binari disponibili per i tipi integrali e a virgola mobile unboxed.

|Operatore binario|Note|
|---------------|-----|
|`+`(addizione, più)|Deselezionata. Possibile condizione di overflow quando i numeri vengono aggiunti insieme e la somma supera il valore assoluto massimo supportato dal tipo.|
|`-`(sottrazione, meno)|Deselezionata. Possibile condizione di underflow quando i tipi non firmati vengono sottratti o quando i valori a virgola mobile sono troppo piccoli per essere rappresentati dal tipo.|
|`*`(moltiplicazione, ore)|Deselezionata. Possibile condizione di overflow quando i numeri vengono moltiplicati e il prodotto supera il valore assoluto massimo supportato dal tipo.|
|`/`(divisione, divisa per)|La divisione per zero causa <xref:System.DivideByZeroException> un per i tipi integrali. Per i tipi a virgola mobile, la divisione per zero fornisce i valori `+Infinity` a virgola mobile speciali o. `-Infinity` È inoltre possibile che si verifichi una condizione di underflow quando un numero a virgola mobile è troppo piccolo per essere rappresentato dal tipo.|
|`%`(resto, REM)|Restituisce il resto di un'operazione di divisione. Il segno del risultato è uguale al segno del primo operando.|
|`**`(elevamento a potenza, alla potenza di)|Possibile condizione di overflow quando il risultato supera il valore assoluto massimo per il tipo.<br /><br />L'operatore di elevamento a potenza funziona solo con i tipi a virgola mobile.|

## <a name="summary-of-unary-arithmetic-operators"></a>Riepilogo degli operatori aritmetici unari

Nella tabella seguente sono riepilogati gli operatori aritmetici unari disponibili per i tipi integrali e a virgola mobile.

|Operatore unario|Note|
|--------------|-----|
|`+`positivo|Può essere applicato a qualsiasi espressione aritmetica. Non modifica il segno del valore.|
|`-`(negazione, negativo)|Può essere applicato a qualsiasi espressione aritmetica. Modifica il segno del valore.|

Il comportamento in fase di overflow o di underflow per i tipi integrali consiste nell'eseguire il wrapping. Questo causa un risultato errato. Un overflow di interi rappresenta un problema potenzialmente grave che può contribuire a problemi di sicurezza quando il software non viene scritto per conto dell'utente. Se questo è un problema per l'applicazione, è consigliabile usare gli operatori selezionati `Microsoft.FSharp.Core.Operators.Checked`in.

## <a name="summary-of-binary-comparison-operators"></a>Riepilogo degli operatori di confronto binario

Nella tabella seguente vengono illustrati gli operatori di confronto binari disponibili per i tipi integrali e a virgola mobile. Questi operatori restituiscono valori di `bool`tipo.

I numeri a virgola mobile non devono mai essere confrontati direttamente per verificarne l'uguaglianza, perché la rappresentazione a virgola mobile IEEE non supporta un'operazione di uguaglianza esatta. Due numeri che è possibile verificare in modo semplice per essere uguali controllando che il codice possa avere effettivamente diverse rappresentazioni di bit.

|Operator|Note|
|--------|-----|
|`=`(uguaglianza, uguale a)|Non si tratta di un operatore di assegnazione. Viene usato solo per il confronto. Si tratta di un operatore generico.|
|`>`(maggiore di)|Si tratta di un operatore generico.|
|`<`(minore di)|Si tratta di un operatore generico.|
|`>=`(maggiore o uguale a)|Si tratta di un operatore generico.|
|`<=`(minore o uguale a)|Si tratta di un operatore generico.|
|`<>`(diverso da)|Si tratta di un operatore generico.|

## <a name="overloaded-and-generic-operators"></a>Operatori generici e di overload

Tutti gli operatori descritti in questo argomento sono definiti nello spazio dei nomi **Microsoft. FSharp. Core. Operators** . Alcuni operatori vengono definiti utilizzando parametri di tipo risolti staticamente. Ciò significa che esistono singole definizioni per ogni tipo specifico che funziona con l'operatore. In questa categoria sono inclusi tutti gli operatori aritmetici, binari e bit per bit. Gli operatori di confronto sono generici e pertanto funzionano con qualsiasi tipo e non solo con tipi aritmetici primitivi. I F# tipi di record e Unione discriminati hanno implementazioni personalizzate generate dal compilatore. I tipi di classe usano <xref:System.Object.Equals%2A>il metodo.

Gli operatori generici sono personalizzabili. Per personalizzare le funzioni di confronto, <xref:System.Object.Equals%2A> eseguire l'override di per fornire un confronto di uguaglianza personalizzato <xref:System.IComparable>, quindi implementare. L' <xref:System.IComparable?displayProperty=nameWithType> interfaccia ha un solo metodo, ovvero <xref:System.IComparable.CompareTo%2A> il metodo.

## <a name="operators-and-type-inference"></a>Operatori e inferenza del tipo

L'utilizzo di un operatore in un'espressione vincola l'inferenza del tipo per l'operatore. Inoltre, l'utilizzo degli operatori impedisce la generalizzazione automatica, perché l'utilizzo di operatori implica un tipo aritmetico. In assenza di altre informazioni, il F# compilatore deduce `int` come il tipo di espressioni aritmetiche. È possibile eseguire l'override di questo comportamento specificando un altro tipo. Pertanto `int`, i tipi di argomento e il `function1` tipo restituito di nel codice seguente vengono dedotti come, ma i tipi per `function2` vengono dedotti `float`come.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per simboli e operatori](index.md)
- [Overload degli operatori](../operator-overloading.md)
- [Operatori bit per bit](bitwise-operators.md)
- [Operatori booleani](boolean-operators.md)
