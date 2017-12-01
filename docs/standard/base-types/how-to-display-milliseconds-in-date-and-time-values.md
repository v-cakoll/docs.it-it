---
title: 'Procedura: visualizzare i millisecondi nei valori data e ora'
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
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Procedura: visualizzare i millisecondi nei valori data e ora
La data e ora predefiniti, i metodi di formattazione, ad esempio <xref:System.DateTime.ToString?displayProperty=nameWithType>, include le ore, minuti e secondi di un valore di ora ma ne esclude componente relativo ai millisecondi. Questo argomento descrive come includere un componente millisecondi di una data e un'ora nelle stringhe di data e ora formattate.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Per visualizzare il componente millisecondi di un valore DateTime  
  
1.  Se si usa la rappresentazione di stringa di una data, convertirla in un valore <xref:System.DateTime> o <xref:System.DateTimeOffset> tramite il metodo statico <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.  
  
2.  Per estrarre la rappresentazione di stringa del componente di millisecondi di un'ora, chiamare il valore di data e ora <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ToString%2A> (metodo) e passare il `fff` o `FFF` modello di formato personalizzato autonoma o con altri formato personalizzato identificatori come il `format` parametro.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene visualizzato il componente di millisecondi di un <xref:System.DateTime> e <xref:System.DateTimeOffset> alla console, solo sia incluso in una stringa di data e l'ora più lunga.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 Il modello di formato `fff` include gli zeri finali nei millisecondi. Il modello di formato `FFF` li elimina. Nell'esempio seguente è illustrata questa differenza.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Uno dei problemi della definizione di un identificatore di formato personalizzato completo che include il componente millisecondi di una data e ora è rappresentato dal fatto che l'identificatore definisce un formato hardcoded che potrebbe non corrispondere alla disposizione degli elementi relativi all'ora delle impostazioni cultura correnti dell'applicazione. Un'alternativa migliore consiste nel recuperare uno della data e ora di modelli di visualizzazione definiti dalle impostazioni cultura correnti <xref:System.Globalization.DateTimeFormatInfo> dell'oggetto e modificalo per includere i millisecondi. L'esempio illustra anche questo approccio. Recupera le impostazioni cultura correnti completo modello di data e ora dal <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> , proprietà e quindi inserisce il modello personalizzato `.ffff` dopo il modello dei secondi. Si noti che nell'esempio viene usata un'espressione regolare per eseguire questa operazione in una sola chiamata al metodo.  
  
 È anche possibile usare un identificatore di formato personalizzato per visualizzare una parte frazionaria di secondi diversa dai millisecondi. Ad esempio, l'identificatore di formato personalizzato `f` o `F` visualizza i decimi di secondo, l'identificatore di formato personalizzato `ff` o `FF` i centesimi di secondo e l'identificatore di formato personalizzato `ffff` o `FFFF` i decimillesimi di secondo. Le parti frazionarie di un millisecondo vengono troncate anziché arrotondate nella stringa restituita. Questi identificatori di formato vengono usati nell'esempio seguente.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  È possibile visualizzare piccolissime unità di secondo frazionarie, come decimillesimi di secondo o centomillesimi di secondo. Questi valori tuttavia potrebbero non essere significativi. La precisione dei valori di data e ora dipende dalla risoluzione del clock di sistema. In Windows NT 3.5 e versioni successive, e [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] sistemi operativi, la risoluzione del clock è di circa 10-15 millisecondi.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Compilare il codice nella riga di comando con csc.exe o vb.exe. Per compilare il codice in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], inserirlo in un modello di progetto applicazione console.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
