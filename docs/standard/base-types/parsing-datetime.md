---
title: Analisi delle stringhe di data e ora in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analisi di stringhe di data e ora in .NET
I metodi di analisi consentono di convertire la rappresentazione di stringa di una data e un'ora in un oggetto <xref:System.DateTime> equivalente. I metodi <xref:System.DateTime.Parse%2A> e <xref:System.DateTime.TryParse%2A> convertono qualsiasi rappresentazione di data e ora tra quelle usate comunemente. I metodi <xref:System.DateTime.ParseExact%2A> e <xref:System.DateTime.TryParseExact%2A> convertono una rappresentazione di stringa conforme al criterio specificato da una stringa di formato di data e ora. Vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 L'analisi è influenzata dalle proprietà di un provider di formato che rende disponibili informazioni quali le stringhe usate per i separatori di data e ora e i nomi di mesi, giorni ed ere. Il provider di formato è l'oggetto <xref:System.Globalization.DateTimeFormatInfo> corrente, che viene definito in modo implicito dalle impostazioni cultura del thread corrente o in modo esplicito dal parametro <xref:System.IFormatProvider> di un metodo di analisi. Per il parametro <xref:System.IFormatProvider>, specificare un oggetto <xref:System.Globalization.CultureInfo>, che rappresenta determinate impostazioni cultura o un oggetto <xref:System.Globalization.DateTimeFormatInfo>.  
  
 La rappresentazione di stringa di una data da analizzare deve includere il mese e almeno un giorno o anno. La rappresentazione di stringa di un'ora deve includere l'ora e almeno i minuti o l'indicazione AM/PM. Se possibile, tuttavia, l'analisi indica i valori predefiniti per i componenti omessi. Per impostazione predefinita, per una data mancante viene indicata la data corrente, per un anno mancante viene indicato l'anno in corso, per un giorno del mese mancante viene indicato il primo giorno del mese e per un'ora mancante viene indicata la mezzanotte.  
  
 Se la rappresentazione di stringa specifica solo l'ora, l'analisi restituisce un oggetto <xref:System.DateTime> con le relative proprietà <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> e <xref:System.DateTime.Day%2A> impostate sui valori corrispondenti della proprietà <xref:System.DateTime.Today%2A>. Tuttavia, se viene specificata la costante <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> nel metodo di analisi, le proprietà relative ad anno, mese e giorno vengono impostate sul valore `1`.  
  
 Oltre a un componente di data e ora, la rappresentazione di stringa di una data e un'ora può includere un offset che indica in che misura l'ora differisce dall'ora UTC (Coordinated Universal Time). Ad esempio, la stringa "2/14/2007 5:32:00 -7:00" definisce un'ora che precede di sette ore l'ora UTC. Se viene omesso l'offset dalla rappresentazione di stringa di un'ora, l'analisi restituisce un oggetto <xref:System.DateTime> con la relativa proprietà <xref:System.DateTime.Kind%2A> impostata su <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Se viene specificato un offset, l'analisi restituisce un oggetto <xref:System.DateTime> con la relativa proprietà <xref:System.DateTime.Kind%2A> impostata su <xref:System.DateTimeKind.Local> e il relativo valore adeguato in base al fuso orario locale del computer. È possibile modificare questo comportamento usando una costante <xref:System.Globalization.DateTimeStyles> con il metodo di analisi.  
  
 Il provider di formato viene usato anche per interpretare una data numerica ambigua. Ad esempio, non risulta chiaro quali componenti della data rappresentata dalla stringa "02/03/04" sono il mese, il giorno e l'anno. In questo caso i componenti vengono interpretati in base all'ordine dei formati di data simili nel provider di formato.  
  
## <a name="parse"></a>Parse  
 L'esempio di codice seguente illustra l'uso del metodo **Parse** per convertire una stringa in un oggetto **DateTime**. In questo esempio vengono usate le impostazioni cultura associate al thread corrente per eseguire l'analisi. Se l'oggetto <xref:System.Globalization.CultureInfo> associato alle impostazioni cultura correnti non è in grado di analizzare la stringa di input, viene generata un'eccezione <xref:System.FormatException>.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 È anche possibile specificare un oggetto **CultureInfo** impostato su una delle impostazioni cultura definite da tale oggetto oppure specificare uno degli oggetti <xref:System.Globalization.DateTimeFormatInfo> standard restituiti dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. L'esempio di codice seguente usa un provider di formato per analizzare una stringa in lingua tedesca in un oggetto **DateTime**. Un oggetto **CultureInfo** che rappresenta le impostazioni cultura de-DE viene definito e passato con la stringa da analizzare per garantire che tale stringa venga analizzata correttamente. Ciò non consente di determinare se l'impostazione è inclusa nell'oggetto **CurrentCulture** dell'oggetto **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Tuttavia, sebbene sia possibile usare overload del metodo <xref:System.DateTime.Parse%2A> per specificare provider di formato personalizzati, il metodo non supporta l'uso di provider di formato non standard. Per analizzare una data e un'ora espresse in un formato non standard, usare il metodo <xref:System.DateTime.ParseExact%2A>.  
  
 Nell'esempio di codice seguente viene usata l'enumerazione <xref:System.Globalization.DateTimeStyles> per specificare che la data e l'ora correnti non devono essere aggiunte a **DateTime** per i campi che la stringa non definisce.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 Il metodo <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> converte una stringa conforme a un modello di stringa specificata in un oggetto **DateTime**. Quando una stringa che non è nel formato specificato viene passata a questo metodo, viene generata un'eccezione <xref:System.FormatException>. È possibile specificare uno degli identificatori di formato di data e ora standard o una combinazione limitata degli identificatori di formato di data e ora personalizzato. Usando gli identificatori di formato personalizzato è possibile costruire una stringa di riconoscimento personalizzata. Per una spiegazione degli identificatori, vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Ogni overload del metodo <xref:System.DateTime.ParseExact%2A> usa anche un parametro <xref:System.IFormatProvider> che in genere indica informazioni specifiche delle impostazioni cultura sulla formattazione della stringa. In genere, questo oggetto <xref:System.IFormatProvider> è un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura standard o un oggetto <xref:System.Globalization.DateTimeFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Tuttavia, a differenza di altre funzioni di analisi di data e ora, questo metodo supporta anche un oggetto <xref:System.IFormatProvider> che definisce un formato di data e ora non standard.  
  
 Nell'esempio di codice seguente, al metodo **ParseExact** viene passato un oggetto stringa da analizzare, seguito da un identificatore di formato, seguito da un oggetto **CultureInfo**. Questo metodo **ParseExact** consente di analizzare solo le stringhe con il modello di data estesa nelle impostazioni cultura en-US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)
