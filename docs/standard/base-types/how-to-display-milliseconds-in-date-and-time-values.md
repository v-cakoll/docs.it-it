---
title: 'Procedura: visualizzare i millisecondi nei valori data e ora'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 36d99753503d9ba4b1bde4143c86ba184674e53e
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960399"
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Procedura: visualizzare i millisecondi nei valori data e ora
I metodi di formattazione di data e ora predefiniti, ad esempio <xref:System.DateTime.ToString?displayProperty=nameWithType>, includono le ore, i minuti e i secondi di un valore di ora, ma ne escludono il componente dei millisecondi. Questo argomento descrive come includere un componente millisecondi di una data e un'ora nelle stringhe di data e ora formattate.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Per visualizzare il componente millisecondi di un valore DateTime  
  
1. Se si usa la rappresentazione di stringa di una data, convertirla in un valore <xref:System.DateTime> o <xref:System.DateTimeOffset> tramite il metodo statico <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.  
  
2. Per estrarre la rappresentazione di stringa del componente dei millisecondi di un'ora, chiamare il metodo <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ToString%2A> del valore di data e ora e passare il modello di formato personalizzato `fff` o `FFF` da solo o con altri identificatori di formato personalizzato come parametro `format`.  
  
## <a name="example"></a>Esempio  
 L'esempio visualizza il componente dei millisecondi di un valore <xref:System.DateTime> e di un valore <xref:System.DateTimeOffset> alla console, sia da solo sia incluso in una stringa di data e ora più lunga.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 Il modello di formato `fff` include gli zeri finali nei millisecondi. Il modello di formato `FFF` li elimina. Nell'esempio seguente è illustrata questa differenza.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Uno dei problemi della definizione di un identificatore di formato personalizzato completo che include il componente millisecondi di una data e ora è rappresentato dal fatto che l'identificatore definisce un formato hardcoded che potrebbe non corrispondere alla disposizione degli elementi relativi all'ora delle impostazioni cultura correnti dell'applicazione. Un'alternativa migliore consiste nel recuperare uno dei modelli di visualizzazione di data e ora definiti dall'oggetto <xref:System.Globalization.DateTimeFormatInfo> delle impostazioni cultura correnti e modificarlo in modo da includere i millisecondi. L'esempio illustra anche questo approccio. L'esempio recupera il modello di data e ora completo delle impostazioni cultura correnti dalla proprietà <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> e quindi inserisce il modello personalizzato `.ffff` dopo il modello dei secondi. Si noti che nell'esempio viene usata un'espressione regolare per eseguire questa operazione in una sola chiamata al metodo.  
  
 È anche possibile usare un identificatore di formato personalizzato per visualizzare una parte frazionaria di secondi diversa dai millisecondi. Ad esempio, l'identificatore di formato personalizzato `f` o `F` visualizza i decimi di secondo, l'identificatore di formato personalizzato `ff` o `FF` i centesimi di secondo e l'identificatore di formato personalizzato `ffff` o `FFFF` i decimillesimi di secondo. Le parti frazionarie di un millisecondo vengono troncate anziché arrotondate nella stringa restituita. Questi identificatori di formato vengono usati nell'esempio seguente.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
> È possibile visualizzare piccolissime unità di secondo frazionarie, come decimillesimi di secondo o centomillesimi di secondo. Questi valori tuttavia potrebbero non essere significativi. La precisione dei valori di data e ora dipende dalla risoluzione del clock di sistema. Nei sistemi operativi Windows NT 3,5 e versioni successive e Windows Vista la risoluzione del clock è di circa 10-15 millisecondi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.DateTimeFormatInfo>
- [Stringhe di formato di data e ora personalizzato](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
