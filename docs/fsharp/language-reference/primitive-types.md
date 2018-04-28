---
title: Tipi primitivi (F#)
description: 'Individuare i tipi primitivi fondamentali utilizzati nel linguaggio F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7832151ee211f56547ecad98fc31f1454cb18870
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="primitive-types"></a>Tipi primitivi

Questo argomento elenca i tipi primitivi fondamentali utilizzati nel linguaggio F #. Specifica anche i tipi .NET corrispondenti e i valori minimi e massimi per ogni tipo.

## <a name="summary-of-primitive-types"></a>Riepilogo dei tipi primitivi
Nella tabella seguente sono riepilogate le proprietà dei tipi primitivi F #.

|Tipo|Tipo .NET|Descrizione|
|----|---------|-----------|
|`bool`|`System.Boolean`|I valori possibili sono `true` e `false`.|
|`byte`|`System.Byte`|Valori compresi tra 0 e 255.|
|`sbyte`|`System.SByte`|Valori compresi tra -128 a 127.|
|`int16`|`System.Int16`|Valori compresi tra -32768 e 32767.|
|`uint16`|`System.UInt16`|Valori compresi tra 0 e 65535.|
|`int`|`System.Int32`|Valori compresi tra -2.147.483.648 e 2.147.483.647.|
|`uint32`|`System.UInt32`|Valori compresi tra 0 e 4.294.967.295.|
|`int64`|`System.Int64`|Valori compresi tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.|
|`uint64`|`System.UInt64`|Valori da 0 a 18.446.744.073.709.551.615.|
|`nativeint`|`System.IntPtr`|Un puntatore nativo come un intero con segno.|
|`unativeint`|`System.UIntPtr`|Un puntatore nativo come un intero senza segno.|
|`char`|`System.Char`|Valori di tipo carattere Unicode.|
|`string`|`System.String`|Testo Unicode.|
|`decimal`|`System.Decimal`|Tipo di dati che ha almeno 28 cifre significative a virgola mobile.|
|`unit`|non applicabile|Indica l'assenza di un valore effettivo. Il tipo ha un solo valore formale, indicato `()`. Il valore dell'unità, `()`, viene spesso utilizzato come segnaposto in cui è necessario un valore ma nessun valore reale è disponibile o ha senso.|
|`void`|`System.Void`|Non indica nessun tipo o valore.|
|`float32, single`|`System.Single`|Tipo a virgola mobile a 32 bit.|
|`float, double`|`System.Double`|Tipo a virgola mobile a 64 bit.|

>[!NOTE]
È possibile eseguire calcoli con numeri interi troppo grande per il tipo integer a 64 bit utilizzando il [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo. `bigint` non viene considerato un tipo primitivo. è un'abbreviazione per `System.Numerics.BigInteger`.

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
