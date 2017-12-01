---
title: Tabelle di conversione dei tipi in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a>Tabelle di conversione dei tipi in .NET
Si parla di conversione verso un tipo di dati più grande quando un valore di un certo tipo viene convertito in un altro tipo di dimensioni identiche o maggiori. Si parla di conversione verso un tipo di dati più piccolo quando un valore di un certo tipo viene convertito in un valore di un altro tipo di dimensioni inferiori. Le tabelle in questo argomento illustrano i comportamenti di entrambi i tipi di conversioni.  
  
## <a name="widening-conversions"></a>conversioni verso un tipo di dati più grande  
 Nella tabella seguente vengono descritte le conversioni di ampliamento che possono essere eseguite senza perdita di informazioni.  
  
|Tipo|Conversione senza perdita di dati in|  
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
  
 Alcune conversioni di ampliamento verso <xref:System.Single> o <xref:System.Double> può causare una perdita di precisione. Nella tabella seguente sono elencate le conversioni verso un tipo di dati più grande che possono generare una perdita di informazioni.  
  
|Tipo|Conversione in|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Conversioni verso <xref:System.Single> o <xref:System.Double> può causare una perdita di informazioni. Se il tipo di destinazione non è in grado di rappresentare in modo appropriato l'ordine di grandezza dell'origine, il tipo risultante viene impostato sulla costante `PositiveInfinity` o `NegativeInfinity`. `PositiveInfinity`risultato della divisione per zero di un numero positivo e viene restituito anche quando il valore di un <xref:System.Single> o <xref:System.Double> supera il valore del `MaxValue` campo. `NegativeInfinity`risultato della divisione per zero di un numero negativo e viene restituito anche quando il valore di un <xref:System.Single> o <xref:System.Double> è inferiore al valore del `MinValue` campo. Una conversione da un <xref:System.Double> per un <xref:System.Single> potrebbe essere `PositiveInfinity` o `NegativeInfinity`.  
  
 Una conversione verso un tipo di dati più piccolo può generare una perdita di informazioni anche per altri tipi di dati. Tuttavia, un <xref:System.OverflowException> viene generata se il valore di un tipo da convertire non rientra nell'intervallo specificato per il tipo di destinazione `MaxValue` e `MinValue` campi e la conversione è controllato dal runtime per assicurarsi che il valore di destinazione tipo non superi il `MaxValue` o `MinValue`. Le conversioni eseguite con la <xref:System.Convert?displayProperty=nameWithType> classe vengono sempre archiviate in questo modo.  
  
 Nella tabella seguente sono elencate le conversioni che generano un <xref:System.OverflowException> utilizzando <xref:System.Convert?displayProperty=nameWithType> o qualsiasi conversione controllata se il valore del tipo da convertire non rientra nell'intervallo specificato per il tipo risultante.  
  
|Tipo|Conversione in|  
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
 <xref:System.Convert?displayProperty=nameWithType>  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)
