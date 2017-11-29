---
title: Tabella di formattazione dei risultati numerici (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce14d5124ffdf030701ae0fc769278da51f86cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabella di formattazione dei risultati numerici (Riferimenti per C#)
È possibile formattare i risultati numerici usando il metodo <xref:System.String.Format%2A?displayProperty=nameWithType> o con il metodo <xref:System.Console.Write%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> che chiama `String.Format`. Il formato è specificato dalle stringhe di formato. La tabella seguente contiene le stringhe di formato standard supportate. La stringa di formato ha questo aspetto: `Axx`, dove `A` è l'identificatore del formato e `xx` è l'identificatore della precisione. L'identificatore del formato controlla il tipo di formattazione applicato al valore numerico e l'identificatore della precisione controlla il numero di cifre significative o di decimali dell'output formattato. Il valore dell'identificatore della precisione è compreso tra 0 e 99.  
  
 Per altre informazioni sulle stringhe di formato numerico standard, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md). Per ulteriori informazioni sul metodo `String.Format`, vedere <xref:System.String.Format%2A?displayProperty=nameWithType>.  
  
|Identificatore di formato|Descrizione|Esempi|Output|  
|----------------------|-----------------|--------------|------------|  
|C o c|Valuta|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D o d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E o e|Scientifico|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F o f|A virgola fissa|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G o g|Generale|Console.Write("{0:G}", 2.5);|2.5|  
|N o n|Number|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X o x|Esadecimale|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)  
 [Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [string](../../../csharp/language-reference/keywords/string.md)
