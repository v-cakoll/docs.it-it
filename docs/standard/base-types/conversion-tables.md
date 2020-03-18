---
title: Tabelle di conversione dei tipi in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
ms.openlocfilehash: aa1ef8397338af949bd147fd3252b2d9ecaf53ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73103881"
---
# <a name="type-conversion-tables-in-net"></a>Tabelle di conversione dei tipi in .NET
Si parla di conversione verso un tipo di dati più grande quando un valore di un certo tipo viene convertito in un altro tipo di dimensioni identiche o maggiori. Si parla di conversione verso un tipo di dati più piccolo quando un valore di un certo tipo viene convertito in un valore di un altro tipo di dimensioni inferiori. Le tabelle in questo argomento illustrano i comportamenti di entrambi i tipi di conversioni.  
  
## <a name="widening-conversions"></a>conversioni verso un tipo di dati più grande  
 Nella tabella seguente sono elencate le conversioni verso un tipo di dati più grande che possono essere eseguite senza la perdita di informazioni.  
  
|Type|Conversione senza perdita di dati in|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Alcune conversioni verso il tipo di dati più grande <xref:System.Single> o <xref:System.Double> possono causare una perdita di precisione. Nella tabella seguente sono elencate le conversioni verso un tipo di dati più grande che possono generare una perdita di informazioni.  
  
|Type|Conversione in|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Alcune conversioni verso il tipo di dati più piccolo <xref:System.Single> o <xref:System.Double> possono causare una perdita di informazioni. Se il tipo di destinazione non è in grado di rappresentare in modo appropriato l'ordine di grandezza dell'origine, il tipo risultante viene impostato sulla costante `PositiveInfinity` o `NegativeInfinity`. `PositiveInfinity` è il risultato della divisione di un numero positivo per zero e viene restituito anche quando il valore di un tipo <xref:System.Single> o <xref:System.Double> supera il valore del campo `MaxValue`. `NegativeInfinity` è il risultato della divisione di un numero negativo per zero e viene restituito anche quando il valore di un tipo <xref:System.Single> o <xref:System.Double> è minore del valore del campo `MinValue`. Una conversione da un tipo <xref:System.Double>Double a un tipo <xref:System.Single> potrebbe avere come risultato un valore `PositiveInfinity` o `NegativeInfinity`.  
  
 Una conversione verso un tipo di dati più piccolo può generare una perdita di informazioni anche per altri tipi di dati. Viene tuttavia generato un evento <xref:System.OverflowException> se il valore di un tipo da convertire non rientra nell'intervallo specificato dai campi `MaxValue` e `MinValue` del tipo di destinazione e il processo di conversione viene controllato dal runtime per poter assicurare che il valore del tipo di destinazione non superi `MaxValue` o `MinValue`. Le conversioni eseguite tramite la classe <xref:System.Convert?displayProperty=nameWithType> vengono sempre controllate in questo modo.  
  
 Nella tabella seguente sono elencate le conversioni che generano un evento <xref:System.OverflowException> tramite <xref:System.Convert?displayProperty=nameWithType> o qualsiasi conversione controllata se il valore del tipo convertito non rientra nell'intervallo specificato per il tipo risultante.  
  
|Type|Conversione in|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Convert?displayProperty=nameWithType>
- [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)
