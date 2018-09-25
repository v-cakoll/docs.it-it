---
title: Operatori bit per bit (F#)
description: 'Informazioni sugli operatori bit per bit che sono disponibili nel linguaggio di programmazione F #.'
ms.date: 07/20/2018
ms.openlocfilehash: ed76fcf5f9c569a2f288cf260e99dc29fd65ef3b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075070"
---
# <a name="bitwise-operators"></a>Operatori bit per bit

Questo argomento descrive gli operatori bit per bit sono disponibili nel linguaggio F #.

## <a name="summary-of-bitwise-operators"></a>Riepilogo degli operatori bit per bit

Nella tabella seguente descrive gli operatori bit per bit supportati per i tipi integrali unboxed nel linguaggio F #.

|Operatore|Note|
|--------|-----|
|`&&&`|Operatore AND bit per bit. I bit nel risultato sono il valore 1 se e solo se i bit corrispondenti in entrambi gli operandi di origine sono pari a 1.|
|<code>&#124;&#124;&#124;</code>|Operatore OR bit per bit. I bit nel risultato sono il valore 1 se entrambi i bit corrispondenti nell'origine gli operandi sono pari a 1.|
|`^^^`|OR bit per bit esclusivo operatore OR. I bit nel risultato sono il valore 1 se e solo se i bit negli operandi di origine hanno valori diversi.|
|`~~~`|Operatore di negazione bit per bit. Questo è un operatore unario e produce un risultato in cui tutti i bit 0 nell'operando di origine vengono convertiti in bit 1 e tutti i bit 1 vengono convertiti in 0 bit.|
|`<<<`|OR bit per bit operatore di spostamento a sinistra. Il risultato è che il primo operando con i bit spostati a sinistra del numero di bit del secondo operando. Bit spostati oltre la posizione più significativa non vengono ruotati in corrispondenza della posizione meno significativo. Il bit meno significativi vengono riempiti con zeri. Il tipo del secondo argomento è `int32`.|
|`>>>`|OR bit per bit operatore di spostamento a destra. Il risultato è il primo operando con i bit spostati a destra del numero di bit del secondo operando. I bit spostati dalla posizione meno significativa non vengono ruotati in posizione più significativa. Per i tipi senza segno, i bit più significativi vengono riempiti con zeri. Per i tipi con segno con valori negativi, i bit più significativi vengono riempiti con quelli. Il tipo del secondo argomento è `int32`.|

I tipi seguenti possono essere utilizzati con gli operatori bit per bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, e `unativeint`.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per simboli e operatori](index.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori booleani](boolean-operators.md)
