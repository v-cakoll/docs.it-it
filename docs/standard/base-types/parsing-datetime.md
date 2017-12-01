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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>L'analisi di stringhe di data e ora in .NET
Metodi di analisi convertono la rappresentazione di stringa di data e ora in un equivalente <xref:System.DateTime> oggetto. Il <xref:System.DateTime.Parse%2A> e <xref:System.DateTime.TryParse%2A> metodi è possibile convertire alcune rappresentazioni comuni di data e ora. Il <xref:System.DateTime.ParseExact%2A> e <xref:System.DateTime.TryParseExact%2A> metodi convertono una rappresentazione di stringa conforme al criterio specificato da una stringa di formato di data e ora. Vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 L'analisi è influenzata dalle proprietà di un provider di formato che rende disponibili informazioni quali le stringhe usate per i separatori di data e ora e i nomi di mesi, giorni ed ere. Il provider di formato è il numero corrente <xref:System.Globalization.DateTimeFormatInfo> oggetto, che viene fornito in modo implicito dalle impostazioni cultura del thread corrente o in modo esplicito dal <xref:System.IFormatProvider> parametro di un metodo di analisi. Per il <xref:System.IFormatProvider> parametro, specificare un <xref:System.Globalization.CultureInfo> oggetto che rappresenta le impostazioni cultura, o un <xref:System.Globalization.DateTimeFormatInfo> oggetto.  
  
 La rappresentazione di stringa di una data da analizzare deve includere il mese e almeno un giorno o anno. La rappresentazione di stringa di un'ora deve includere l'ora e almeno i minuti o l'indicazione AM/PM. Se possibile, tuttavia, l'analisi indica i valori predefiniti per i componenti omessi. Per impostazione predefinita, per una data mancante viene indicata la data corrente, per un anno mancante viene indicato l'anno in corso, per un giorno del mese mancante viene indicato il primo giorno del mese e per un'ora mancante viene indicata la mezzanotte.  
  
 Se la rappresentazione di stringa specificata solo l'ora, l'analisi restituisce un <xref:System.DateTime> dell'oggetto con il relativo <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, e <xref:System.DateTime.Day%2A> impostate sui valori corrispondenti del <xref:System.DateTime.Today%2A> proprietà. Tuttavia, se il <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> (costante) viene specificata il metodo di analisi, risulta anno, mese e giorno sono impostate sul valore `1`.  
  
 Oltre a un componente di data e ora, la rappresentazione di stringa di una data e un'ora può includere un offset che indica in che misura l'ora differisce dall'ora UTC (Coordinated Universal Time). Ad esempio, la stringa "2/14/2007 5:32:00 -7:00" definisce un'ora che precede di sette ore l'ora UTC. Se viene omesso l'offset dalla rappresentazione di stringa di un'ora, l'analisi restituisce un <xref:System.DateTime> dell'oggetto con il relativo <xref:System.DateTime.Kind%2A> proprietà impostata su <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Se viene specificato un offset, l'analisi restituisce un <xref:System.DateTime> dell'oggetto con il relativo <xref:System.DateTime.Kind%2A> proprietà impostata su <xref:System.DateTimeKind.Local> e il relativo valore regolato per il fuso orario locale del computer. È possibile modificare questo comportamento utilizzando un <xref:System.Globalization.DateTimeStyles> costante con il metodo di analisi.  
  
 Il provider di formato viene usato anche per interpretare una data numerica ambigua. Ad esempio, non risulta chiaro quali componenti della data rappresentata dalla stringa "02/03/04" sono il mese, il giorno e l'anno. In questo caso i componenti vengono interpretati in base all'ordine dei formati di data simili nel provider di formato.  
  
## <a name="parse"></a>Parse  
 Esempio di codice seguente viene illustrato l'utilizzo del **analizzare** metodo per convertire una stringa in un **DateTime**. In questo esempio vengono usate le impostazioni cultura associate al thread corrente per eseguire l'analisi. Se il <xref:System.Globalization.CultureInfo> associato all'oggetto corrente delle impostazioni cultura non è possibile analizzare la stringa di input, un <xref:System.FormatException> viene generata un'eccezione.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 È inoltre possibile specificare un **CultureInfo** impostato su una delle impostazioni cultura definite da tale oggetto, oppure è possibile specificare una dello standard <xref:System.Globalization.DateTimeFormatInfo> gli oggetti restituiti dal <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> proprietà. Esempio di codice seguente viene utilizzato un provider di formato per analizzare una stringa in lingua tedesca in un **DateTime**. Oggetto **CultureInfo** che rappresenta le impostazioni cultura de-DE viene definito e può essere passato con la stringa da analizzare per assicurare che l'esito positivo. In questo modo l'impostazione nel **CurrentCulture** del **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Tuttavia, sebbene sia possibile utilizzare l'overload di <xref:System.DateTime.Parse%2A> per specificare il provider di formato personalizzato, il metodo non supporta l'utilizzo di provider di formato non standard. Per analizzare una data e ora espresse in un formato non standard, usare il <xref:System.DateTime.ParseExact%2A> metodo invece.  
  
 Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Globalization.DateTimeStyles> enumerazione per specificare che le informazioni di data e l'ora corrente non devono essere aggiunto al **DateTime** per i campi che non definisce la stringa.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 Il <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> metodo converte una stringa conforme a un modello di stringa specificata in un **DateTime** oggetto. Quando viene passata una stringa che non è nel formato specificato a questo metodo, un <xref:System.FormatException> viene generata un'eccezione. È possibile specificare uno degli identificatori di formato di data e ora standard o una combinazione limitata degli identificatori di formato di data e ora personalizzato. Usando gli identificatori di formato personalizzato è possibile costruire una stringa di riconoscimento personalizzata. Per una spiegazione degli identificatori, vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Ogni overload del <xref:System.DateTime.ParseExact%2A> metodo presenta inoltre un <xref:System.IFormatProvider> parametro che in genere fornisce informazioni specifiche delle impostazioni cultura sulla formattazione della stringa. In genere, questa <xref:System.IFormatProvider> oggetto è un <xref:System.Globalization.CultureInfo> oggetto che rappresenta le impostazioni cultura standard o un <xref:System.Globalization.DateTimeFormatInfo> oggetto restituito dal <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> proprietà. Tuttavia, a differenza di altri data e ora di funzioni di analisi, questo metodo supporta anche un <xref:System.IFormatProvider> che definisce un non standard formato data e ora.  
  
 Nell'esempio di codice seguente, il **ParseExact** viene passato un oggetto stringa da analizzare, seguito da un identificatore di formato, seguito da un **CultureInfo** oggetto. Questo **ParseExact** metodo consente di analizzare solo le stringhe con il modello di data estesa nelle impostazioni cultura en-US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi di stringhe](../../../docs/standard/base-types/parsing-strings.md)  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)  
 [Conversione di tipi in .NET](../../../docs/standard/base-types/type-conversion.md)
