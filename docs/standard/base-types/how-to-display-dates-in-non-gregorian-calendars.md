---
title: 'Procedura: Visualizzare le date in calendari non gregoriani'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
ms.openlocfilehash: 8d02b74f63ec5b6260679ae4cea04791681ec238
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523921"
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Procedura: Visualizzare le date in calendari non gregoriani
I tipi <xref:System.DateTime> e <xref:System.DateTimeOffset> e usano il calendario gregoriano come calendario predefinito. Ciò significa che la chiamata al metodo `ToString` di un valore di data e ora visualizza la rappresentazione di stringa di tale data e ora nel calendario gregoriano, anche se la data e l'ora sono state create usando un altro calendario. Questo processo viene mostrato nell'esempio seguente, che usa due modi diversi per creare un valore di data e ora con il calendario persiano, continuando a visualizzare questi valori di data e ora nel calendario gregoriano quando viene chiamato il metodo <xref:System.DateTime.ToString%2A>. L'esempio riflette due tecniche comuni ma non corrette per la visualizzazione della data in un determinato calendario.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Per visualizzare la data in un determinato calendario è possibile usare due tecniche differenti. La prima richiede che il calendario sia il calendario predefinito per determinate impostazioni cultura. La seconda può essere usata con qualsiasi calendario.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Per visualizzare la data per il calendario predefinito di determinate impostazione cultura  
  
1. Creare un'istanza di un oggetto calendario derivato dalla classe <xref:System.Globalization.Calendar> che rappresenta il calendario da usare.  
  
2. Creare un'istanza di un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura la cui formattazione verrà usata per visualizzare la data.  
  
3. Chiamare il metodo <xref:System.Array.Exists%2A?displayProperty=nameWithType> per determinare se l'oggetto calendario è un membro della matrice restituita dalla proprietà <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Questo indica che il calendario può diventare il calendario predefinito per l'oggetto <xref:System.Globalization.CultureInfo>. Se non è un membro della matrice, seguire le istruzioni riportate nella sezione "Per visualizzare la data in qualsiasi calendario".  
  
4. Assegnare l'oggetto calendario alla proprietà <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> dell'oggetto <xref:System.Globalization.DateTimeFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > La classe <xref:System.Globalization.CultureInfo> include anche una proprietà <xref:System.Globalization.CultureInfo.Calendar%2A>. È tuttavia costante e di sola lettura e non viene modificata per riflettere il nuovo calendario predefinito assegnato alla proprietà <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>.  
  
5. Chiamare il metodo <xref:System.DateTime.ToString%2A> o <xref:System.DateTime.ToString%2A> e passare al metodo l'oggetto <xref:System.Globalization.CultureInfo> il cui calendario predefinito è stato modificato nel passaggio precedente.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Per visualizzare la data in qualsiasi calendario  
  
1. Creare un'istanza di un oggetto calendario derivato dalla classe <xref:System.Globalization.Calendar> che rappresenta il calendario da usare.  
  
2. Determinare gli elementi di data e ora da visualizzare nella rappresentazione di stringa del valore di data e ora.  
  
3. Per ogni elemento di data e ora che si vuole visualizzare, chiamare il metodo `Get` dell'oggetto calendario. ProcessOnStatus. Sono disponibili i metodi seguenti:  
  
    - <xref:System.Globalization.Calendar.GetYear%2A>, per visualizzare l'anno nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetMonth%2A>, per visualizzare il mese nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, per visualizzare il numero del giorno e del mese nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetHour%2A>, per visualizzare l'ora del giorno nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetMinute%2A>, per visualizzare i minuti dell'ora nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetSecond%2A>, per visualizzare i secondi del minuto nel calendario appropriato.  
  
    - <xref:System.Globalization.Calendar.GetMilliseconds%2A>, per visualizzare i millisecondi del secondo nel calendario appropriato.  
  
## <a name="example"></a>Esempio  
 L'esempio visualizza una data usando due calendari diversi. La data viene visualizzata dopo aver definito il calendario Hijri come calendario predefinito per le impostazioni cultura ar-JO e usando il calendario persiano che non è supportato come calendario facoltativo nelle impostazioni cultura fa-IR.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Ogni oggetto <xref:System.Globalization.CultureInfo> può supportare uno o più calendari, indicati dalla proprietà <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>. Uno di questi è designato come calendario predefinito delle impostazioni cultura e viene restituito dalla proprietà <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> di sola lettura. È possibile designare come predefinito un altro calendario tra quelli facoltativi assegnando un oggetto <xref:System.Globalization.Calendar> che rappresenta il calendario alla proprietà <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> restituita dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Tuttavia, alcuni calendari, ad esempio quello persiano rappresentato dalla classe <xref:System.Globalization.PersianCalendar>, non vengono usati come calendari facoltativi per alcuna delle impostazioni cultura.  
  
 Nell'esempio viene definita la classe dell'utilità di calendario riutilizzabile `CalendarUtility` per gestire molti dei dettagli relativi alla generazione della rappresentazione di stringa di una data mediante un determinato calendario. La classe `CalendarUtility` ha i seguenti membri:  
  
- Un costruttore con parametri il cui unico parametro è un oggetto <xref:System.Globalization.Calendar> in cui deve essere rappresentata una data. Viene assegnato a un campo privato della classe.  
  
- `CalendarExists`, metodo privato che restituisce un valore booleano indicante se il calendario rappresentato dall'oggetto `CalendarUtility` è supportato dall'oggetto <xref:System.Globalization.CultureInfo> passato al metodo come parametro. Il metodo esegue il wrapping di una chiamata al metodo <xref:System.Array.Exists%2A?displayProperty=nameWithType>, a cui passa la matrice <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>.  
  
- `HasSameName`, metodo privato assegnato al delegato <xref:System.Predicate%601> che viene passato come parametro al metodo <xref:System.Array.Exists%2A?displayProperty=nameWithType>. Ogni membro della matrice viene passato al metodo finché quest'ultimo non restituisce `true`. Il metodo determina se il nome di un calendario facoltativo è identico a quello del calendario rappresentato dall'oggetto `CalendarUtility`.  
  
- `DisplayDate`, metodo pubblico in overload a cui vengono passati due parametri: un valore <xref:System.DateTime> o <xref:System.DateTimeOffset> da esprimere nel calendario rappresentato dall'oggetto`CalendarUtility` e le impostazioni cultura di cui usare le regole di formattazione. Il comportamento nella restituzione della rappresentazione di stringa di una data varia a seconda che il calendario di destinazione sia supportato dalle impostazioni cultura le cui regole di formattazione devono essere usate.  
  
 Indipendentemente dal calendario usato per creare un valore <xref:System.DateTime> o <xref:System.DateTimeOffset> in questo esempio, il valore viene in genere espresso come data del calendario gregoriano. Il motivo è che i tipi <xref:System.DateTime> e <xref:System.DateTimeOffset> non mantengono le informazioni sul calendario. Internamente vengono rappresentati come numero di cicli trascorsi dopo la mezzanotte del 1 gennaio 0001. L'interpretazione del numero dipende dal calendario. Per la maggior parte delle impostazioni cultura, il calendario predefinito è il calendario gregoriano.
