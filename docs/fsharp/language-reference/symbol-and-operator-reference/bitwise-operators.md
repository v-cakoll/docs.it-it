---
title: Operatori bit per bit (F#)
description: 'Informazioni sugli operatori bit per bit disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a>Operatori bit per bit

Questo argomento descrive gli operatori bit per bit sono disponibili nel linguaggio F #.

## <a name="summary-of-bitwise-operators"></a>Riepilogo degli operatori bit per bit
Nella tabella seguente descrive gli operatori bit per bit supportati per i tipi integrali unboxed nel linguaggio F #.

|Operatore|Note|
|--------|-----|
|`&&&`|Operatore AND bit per bit. I bit nel risultato hanno il valore 1 solo se i bit corrispondenti in entrambi gli operandi di origine sono 1.|
|<code>&#124;&#124;&#124;</code>|Operatore OR bit per bit. I bit nel risultato hanno il valore 1 se entrambi i bit corrispondenti nell'origine gli operandi sono di 1.|
|`^^^`|Bit per bit esclusivo operatore OR. I bit nel risultato hanno il valore 1 se e solo se i bit negli operandi di origine hanno valori uguali.|
|`~~~`|Operatore di negazione bit per bit. Questo è un operatore unario e produce un risultato in cui tutti i bit 0 nell'operando di origine vengono convertiti in bit 1 e tutti i componenti di 1 vengono convertiti in bit 0.|
|`<<<`|Bit per bit (operatore di spostamento a sinistra). Il risultato è che il primo operando con i bit spostati a sinistra del numero di bit nel secondo operando. I bit spostati dalla posizione più significativa non vengono ruotati nella posizione meno significativa. Il bit meno significativi vengono riempite con zeri. Il tipo del secondo argomento è `int32`.|
|`>>>`|Bit per bit (operatore di spostamento a destra). Il risultato è il primo operando con i bit spostati a destra del numero di bit nel secondo operando. I bit spostati dalla posizione meno significativa non vengono ruotati nella posizione più significativa. Per i tipi senza segno, il bit più significativi vengono riempite con zeri. Per i tipi con segno, il bit più significativi vengono riempiti con quelle. Il tipo del secondo argomento è `int32`.|

I tipi seguenti sono utilizzabili con operatori bit per bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, e `unativeint`.

## <a name="see-also"></a>Vedere anche
[Riferimenti per simboli e operatori](index.md)

[Operatori aritmetici](arithmetic-operators.md)

[Operatori booleani](boolean-operators.md)

