---
title: 'Tipi di base (F #)'
description: 'Individua i tipi di base fondamentali usati nel linguaggio F #.'
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991012"
---
# <a name="basic-types"></a>Tipi di base

Questo argomento elenca i tipi di base che sono definiti nel linguaggio F #. Questi tipi sono il più fondamentale in F #, che costituiscono la base di quasi tutti i programmi F #. Sono un soprainsieme di tipi primitivi di .NET.

|Tipo|Tipo .NET|Descrizione|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|I valori possibili sono `true` e `false`.|
|`byte`|<xref:System.Byte>|Valori compresi tra 0 e 255.|
|`sbyte`|<xref:System.SByte>|Valori compresi tra -128 e 127.|
|`int16`|<xref:System.Int16>|Valori compresi tra -32768 e 32767.|
|`uint16`|<xref:System.UInt16>|Valori compresi tra 0 e 65535.|
|`int`|<xref:System.Int32>|Valori compresi tra -2.147.483.648 e 2.147.483.647.|
|`uint32`|<xref:System.UInt32>|Valori compresi tra 0 e 4.294.967.295.|
|`int64`|<xref:System.Int64>|Valori compresi tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.|
|`uint64`|<xref:System.UInt64>|Valori compresi tra 0 e 18.446.744.073.709.551.615.|
|`nativeint`|<xref:System.IntPtr>|Un puntatore nativo come un intero con segno.|
|`unativeint`|<xref:System.UIntPtr>|Un puntatore nativo come intero senza segno.|
|`char`|<xref:System.Char>|Valori di tipo carattere Unicode.|
|`string`|<xref:System.String>|Testo Unicode.|
|`decimal`|<xref:System.Decimal>|Tipo di dati che dispone di almeno 28 cifre significative a virgola mobile.|
|`unit`|non applicabile|Indica l'assenza di un valore effettivo. Il tipo ha un solo valore formale, indicato `()`. Il valore dell'unità, `()`, viene spesso usato come segnaposto in cui è necessario un valore ma nessun valore reale è disponibile o ha senso.|
|`void`|<xref:System.Void>|Non indica nessun tipo o valore.|
|`float32`, `single`|<xref:System.Single>|Tipo a virgola mobile a 32 bit.|
|`float`, `double`|<xref:System.Double>|Un tipo a virgola mobile a 64 bit.|

>[!NOTE]
È possibile eseguire calcoli con numeri interi troppo grande per il tipo integer a 64 bit utilizzando il [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo. `bigint` non è considerato un tipo di base. è un'abbreviazione per `System.Numerics.BigInteger`.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
