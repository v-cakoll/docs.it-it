---
title: Convertire stringhe in DateTime
description: Informazioni sulle tecniche per analizzare le stringhe che rappresentano date e ore per creare un oggetto DateTime dalla stringa di data e ora.
ms.date: 02/15/2018
ms.technology: dotnet-standard
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
ms.openlocfilehash: 4b3f0bdb3ade784f929718a3350ed3dec0c572f1
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242647"
---
# <a name="parse-date-and-time-strings-in-net"></a>Analizzare le stringhe di data e ora in .NETParse date and time strings in .NET

L'analisi delle stringhe per convertirle in oggetti <xref:System.DateTime> richiede di specificare informazioni sulla modalità di rappresentazione di date e ore come testo. Impostazioni cultura diverse usano ordini differenti per giorno, mese e anno. Alcune rappresentazioni di ora usano un orologio di 24 ore, altre specificano "AM" e "PM". Alcune applicazioni richiedono solo la data, mentre altre solo l'ora e altre ancora devono specificare sia la data che l'ora. I metodi per la conversione di stringhe in oggetti <xref:System.DateTime> consentono di fornire informazioni dettagliate sui formati previsti e sugli elementi di data e ora necessari per l'applicazione. La conversione corretta di testo in un oggetto <xref:System.DateTime> include tre sottoattività:

1. È necessario specificare il formato previsto del testo che rappresenta una data e ora.
1. È possibile specificare le impostazioni cultura per il formato di una data e ora.
1. È possibile specificare come impostare nella data e ora i componenti mancanti nella rappresentazione di testo.

I metodi <xref:System.DateTime.Parse%2A> e <xref:System.DateTime.TryParse%2A> consentono di convertire molte rappresentazioni comuni di data e ora. I metodi <xref:System.DateTime.ParseExact%2A> e <xref:System.DateTime.TryParseExact%2A> convertono una rappresentazione di stringa conforme al criterio specificato da una stringa di formato di data e ora. Per altri dettagli, vedere gli articoli relativi alle [stringhe di formato di data e ora standard](standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](custom-date-and-time-format-strings.md).

L'oggetto <xref:System.Globalization.DateTimeFormatInfo> corrente consente un maggiore controllo sulla modalità di interpretazione del testo come data e ora. Le proprietà di un oggetto <xref:System.Globalization.DateTimeFormatInfo> descrivono i separatori di data e ora, i nomi di mesi, giorni ed ere, nonché il formato per gli indicatori "AM" e "PM". Le impostazioni cultura del thread corrente forniscono un oggetto <xref:System.Globalization.DateTimeFormatInfo> che rappresenta le impostazioni cultura correnti. Se si vogliono usare impostazioni cultura specifiche o impostazioni personalizzate, specificare il parametro <xref:System.IFormatProvider> di un metodo di analisi. Per il parametro <xref:System.IFormatProvider>, specificare un oggetto <xref:System.Globalization.CultureInfo>, che rappresenta determinate impostazioni cultura o un oggetto <xref:System.Globalization.DateTimeFormatInfo>.

Nel testo che rappresenta una data o ora è possibile che manchino alcune informazioni. Ad esempio, la maggior parte delle persone dedurrebbe che la data "12 marzo" rappresenta l'anno corrente. In modo analogo, "marzo 2018" rappresenta il mese di marzo nell'anno 2018. Il testo che rappresenta l'ora spesso include solo ore e minuti e l'indicatore AM/PM.  I metodi di analisi gestiscono le informazioni mancanti usando impostazioni predefinite ragionevoli:

- Quando è presente solo l'ora, per la parte relativa alla data viene usata la data corrente.
- Se è presente solo la data, la parte dell'ora è mezzanotte.
- Se l'anno non è specificato in una data, viene usato l'anno corrente.
- Quando non viene specificato il giorno del mese, viene usato il primo giorno del mese.

Se la stringa include la data, deve essere incluso il mese e un giorno o un anno. Se è presente l'ora, deve includere l'ora e i minuti o l'indicatore AM/PM.

È possibile specificare la costante <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> per sostituire queste impostazioni predefinite. Quando si usa questa costante, le eventuali proprietà mancanti per anno, mese o giorno vengono impostate sul valore `1`. L'[ultimo esempio](#styles-example) che usa <xref:System.DateTime.Parse%2A> dimostra questo comportamento.

Oltre a un componente di data e ora, la rappresentazione di stringa di una data e un'ora può includere un offset che indica in che misura l'ora differisce dall'ora UTC (Coordinated Universal Time). Ad esempio, la stringa "2/14/2007 5:32:00 -7:00" definisce un'ora che precede di sette ore l'ora UTC. Se viene omesso l'offset dalla rappresentazione di stringa di un'ora, l'analisi restituisce un oggetto <xref:System.DateTime> con la relativa proprietà <xref:System.DateTime.Kind%2A> impostata su <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Se viene specificato un offset, l'analisi restituisce un oggetto <xref:System.DateTime> con la relativa proprietà <xref:System.DateTime.Kind%2A> impostata su <xref:System.DateTimeKind.Local?displayProperty=nameWithType> e il relativo valore adeguato in base al fuso orario locale del computer. È possibile modificare questo comportamento usando un valore <xref:System.Globalization.DateTimeStyles> con il metodo di analisi.
  
Il provider di formato viene usato anche per interpretare una data numerica ambigua. Non risulta chiaro quali componenti della data rappresentata dalla stringa "02/03/04" sono il mese, il giorno e l'anno. I componenti vengono interpretati in base all'ordine dei formati di data simili nel provider di formato.

## <a name="parse"></a>Analizza

L'esempio seguente illustra l'uso del metodo <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> per convertire un valore `string` in <xref:System.DateTime>. Questo esempio usa le impostazioni cultura associate al thread corrente. Se l'oggetto <xref:System.Globalization.CultureInfo> associato alle impostazioni cultura correnti non è in grado di analizzare la stringa di input, viene generata un'eccezione <xref:System.FormatException>.

> [!TIP]
> Tutti gli esempi C# in questo articolo vengono eseguiti nel browser. Premere il pulsante **Run** (Esegui) per visualizzare l'output. È anche possibile modificarli per sperimentare.

> [!NOTE]
> Questi esempi sono disponibili nel repository GitHub docs [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/how-to/conversions)sia per [C.](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/conversions) In alternativa, è possibile scaricare il progetto come file zip per [C ,](https://github.com/dotnet/docs/blob/master/samples/snippets/csharp/how-to/conversions.zip) o [Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/how-to/conversions.zip).

[!code-csharp-interactive[Parsing.DateAndTime#1](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#1)]
[!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#1)]

È anche possibile definire in modo esplicito le impostazioni cultura di cui usare le convenzioni di formattazione per l'analisi di una stringa. È necessario specificare uno degli oggetti <xref:System.Globalization.DateTimeFormatInfo> standard restituiti dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. L'esempio seguente usa un provider di formato per analizzare una stringa in lingua tedesca in un <xref:System.DateTime>. Crea un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura `de-DE`. L'oggetto `CultureInfo` assicura l'analisi corretta di questa stringa particolare. Questo preclude qualsiasi impostazione in <xref:System.Threading.Thread.CurrentCulture> di <xref:System.Threading.Thread.CurrentThread>.  
  
[!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#2)]
[!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#2)]

Tuttavia, sebbene sia possibile usare overload del metodo <xref:System.DateTime.Parse%2A> per specificare provider di formato personalizzati, il metodo non supporta l'analisi di formati non standard. Per analizzare una data e un'ora espresse in un formato non standard, usare il metodo <xref:System.DateTime.ParseExact%2A>.  

<a name="styles-example"></a>L'esempio seguente usa l'enumerazione <xref:System.Globalization.DateTimeStyles> per specificare che le informazioni sulla data e l'ora correnti non devono essere aggiunte a <xref:System.DateTime> per i campi non specificati.  

[!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#3)]
[!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#3)]

## <a name="parseexact"></a>ParseExact

Il metodo <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> converte una stringa in un oggetto <xref:System.DateTime> se è conforme a uno dei modelli di stringa specificati. Quando una stringa che non è in uno dei formati specificati viene passata a questo metodo, viene generata un'eccezione <xref:System.FormatException>. È possibile specificare uno degli identificatori di formato di data e ora standard o una combinazione degli identificatori di formato personalizzato. Usando gli identificatori di formato personalizzato è possibile costruire una stringa di riconoscimento personalizzata. Per una spiegazione degli identificatori, vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](standard-date-and-time-format-strings.md) e alle [stringhe di formato di data e ora personalizzato](custom-date-and-time-format-strings.md).  

Nell'esempio seguente, al metodo <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> viene passato un oggetto stringa da analizzare, seguito da un identificatore di formato, seguito da un oggetto <xref:System.Globalization.CultureInfo>. Questo metodo <xref:System.DateTime.ParseExact%2A> consente di analizzare solo le stringhe con il modello di data estesa nelle impostazioni cultura `en-US`.  

[!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#4)]
[!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#4)]

Ogni overload dei metodi <xref:System.DateTime.Parse%2A> e <xref:System.DateTime.ParseExact%2A> usa anche un parametro <xref:System.IFormatProvider> che indica informazioni specifiche delle impostazioni cultura sulla formattazione della stringa. Questo oggetto <xref:System.IFormatProvider> è un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura standard o un oggetto <xref:System.Globalization.DateTimeFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  <xref:System.DateTime.ParseExact%2A> usa anche un argomento stringa o matrice di stringhe aggiuntivo che definisce uno o più formati di data e ora personalizzati.  

## <a name="see-also"></a>Vedere anche

- [Analisi di stringhe](parsing-strings.md)
- [Formattazione di tipi](formatting-types.md)
- [Conversione dei tipi in .NETType Conversion in .NET](type-conversion.md)
- [Formati di data e ora standard](standard-date-and-time-format-strings.md)
- [Stringhe di formato di data e ora personalizzato](custom-date-and-time-format-strings.md)
