---
title: 'Procedura: Visualizzare le date in calendari non gregoriani'
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
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Procedura: Visualizzare le date in calendari non gregoriani
Il <xref:System.DateTime> e <xref:System.DateTimeOffset> tipi utilizzano il calendario gregoriano come calendario predefinito. Ciò significa che la chiamata al metodo `ToString` di un valore di data e ora visualizza la rappresentazione di stringa di tale data e ora nel calendario gregoriano, anche se la data e l'ora sono state create usando un altro calendario. Come illustrato nell'esempio seguente, che vengono utilizzate due diverse modalità per creare un valore di data e ora con il calendario persiano, ma visualizza ancora tali valori di data e ora nel calendario gregoriano quando viene chiamata la <xref:System.DateTime.ToString%2A> metodo. L'esempio riflette due tecniche comuni ma non corrette per la visualizzazione della data in un determinato calendario.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Per visualizzare la data in un determinato calendario è possibile usare due tecniche differenti. La prima richiede che il calendario sia il calendario predefinito per determinate impostazioni cultura. La seconda può essere usata con qualsiasi calendario.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Per visualizzare la data per il calendario predefinito di determinate impostazione cultura  
  
1.  Creare un'istanza derivato da un oggetto di calendario di <xref:System.Globalization.Calendar> classe che rappresenta il calendario da utilizzare.  
  
2.  Creare un'istanza di un <xref:System.Globalization.CultureInfo> oggetto che rappresenta le impostazioni cultura con formattazione verrà utilizzata per visualizzare la data.  
  
3.  Chiamare il <xref:System.Array.Exists%2A?displayProperty=nameWithType> metodo per determinare se l'oggetto del calendario è un membro della matrice restituita dal <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> proprietà. Ciò indica che il calendario può essere utilizzato come il calendario predefinito per il <xref:System.Globalization.CultureInfo> oggetto. Se non è un membro della matrice, seguire le istruzioni riportate nella sezione "Per visualizzare la data in qualsiasi calendario".  
  
4.  Assegnare l'oggetto di calendario per la <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> proprietà del <xref:System.Globalization.DateTimeFormatInfo> oggetto restituito dal <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> proprietà.  
  
    > [!NOTE]
    >  Il <xref:System.Globalization.CultureInfo> classe include inoltre un <xref:System.Globalization.CultureInfo.Calendar%2A> proprietà. Tuttavia, è di sola lettura e costante; non viene modificato per riflettere il nuovo calendario predefinito assegnato per il <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> proprietà.  
  
5.  Chiamare il <xref:System.DateTime.ToString%2A> o <xref:System.DateTime.ToString%2A> (metodo) e passare il <xref:System.Globalization.CultureInfo> oggetto il cui calendario predefinito è stata modificata nel passaggio precedente.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Per visualizzare la data in qualsiasi calendario  
  
1.  Creare un'istanza derivato da un oggetto di calendario di <xref:System.Globalization.Calendar> classe che rappresenta il calendario da utilizzare.  
  
2.  Determinare gli elementi di data e ora da visualizzare nella rappresentazione di stringa del valore di data e ora.  
  
3.  Per ogni elemento di data e ora che si desidera visualizzare, chiamare l'oggetto di calendario `Get`... ProcessOnStatus. Sono disponibili i metodi seguenti:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>, per visualizzare l'anno nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>, per visualizzare il mese nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, per visualizzare il numero del giorno del mese nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>, per visualizzare l'ora del giorno nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>, per visualizzare i minuti dell'ora nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>, per visualizzare i secondi del minuto nel calendario appropriato.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>, per visualizzare il numero di millisecondi al secondo nel calendario appropriato.  
  
## <a name="example"></a>Esempio  
 L'esempio visualizza una data usando due calendari diversi. La data viene visualizzata dopo aver definito il calendario Hijri come calendario predefinito per le impostazioni cultura ar-JO e usando il calendario persiano che non è supportato come calendario facoltativo nelle impostazioni cultura fa-IR.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Ogni <xref:System.Globalization.CultureInfo> oggetto può supportare uno o più calendari indicati dal <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> proprietà. Uno di questi è designato come calendario predefinito delle impostazioni cultura e viene restituito da sola lettura <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> proprietà. Un altro calendario facoltativo può essere designato come il valore predefinito tramite l'assegnazione di un <xref:System.Globalization.Calendar> oggetto che rappresenta il calendario dal <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> restituito dalla proprietà di <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> proprietà. Tuttavia, alcuni calendari, ad esempio il calendario persiano rappresentato dalla <xref:System.Globalization.PersianCalendar> classe, non come calendari facoltativi per tutte le impostazioni cultura.  
  
 Nell'esempio viene definita la classe dell'utilità di calendario riutilizzabile `CalendarUtility` per gestire molti dei dettagli relativi alla generazione della rappresentazione di stringa di una data mediante un determinato calendario. La classe `CalendarUtility` ha i seguenti membri:  
  
-   Un costruttore con parametri a cui l'unico parametro è un <xref:System.Globalization.Calendar> oggetto in cui deve essere rappresentato una data. Viene assegnato a un campo privato della classe.  
  
-   `CalendarExists`, un metodo privato che restituisce un valore booleano che indica se il calendario è rappresentato dal `CalendarUtility` l'oggetto è supportato per il <xref:System.Globalization.CultureInfo> oggetto passato come parametro al metodo. Il metodo esegue il wrapping di una chiamata al <xref:System.Array.Exists%2A?displayProperty=nameWithType> (metodo), a cui passa il <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> matrice.  
  
-   `HasSameName`, un metodo privato assegnato per il <xref:System.Predicate%601> delegato che viene passato come parametro per il <xref:System.Array.Exists%2A?displayProperty=nameWithType> metodo. Ogni membro della matrice viene passato al metodo finché quest'ultimo non restituisce `true`. Il metodo determina se il nome di un calendario facoltativo è identico a quello del calendario rappresentato dall'oggetto `CalendarUtility`.  
  
-   `DisplayDate`, un metodo pubblico di overload che verrà passato due parametri: sia un <xref:System.DateTime> o <xref:System.DateTimeOffset> express nel calendario rappresentato dal valore di `CalendarUtility` oggetto e le impostazioni cultura le cui regole di formattazione da utilizzare. Il comportamento nella restituzione della rappresentazione di stringa di una data varia a seconda che il calendario di destinazione sia supportato dalle impostazioni cultura le cui regole di formattazione devono essere usate.  
  
 Indipendentemente dal calendario usato per creare un <xref:System.DateTime> o <xref:System.DateTimeOffset> valore in questo esempio, il valore viene in genere espresso come data del calendario gregoriano. In questo modo il <xref:System.DateTime> e <xref:System.DateTimeOffset> tipi non mantengono le informazioni del calendario. Internamente vengono rappresentati come numero di cicli trascorsi dopo la mezzanotte del 1 gennaio 0001. L'interpretazione del numero dipende dal calendario. Per la maggior parte delle impostazioni cultura, il calendario predefinito è il calendario gregoriano.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 In questo esempio richiede un riferimento a System.Core.dll.  
  
 Compilare il codice nella riga di comando con csc.exe o vb.exe. Per compilare il codice in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], inserirlo in un modello di progetto applicazione console.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)
