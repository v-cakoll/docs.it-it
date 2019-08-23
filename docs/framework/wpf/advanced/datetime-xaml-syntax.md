---
title: Sintassi DateTime XAML
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 36066d6b2405051a3d35befffe53af8895e26220
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964839"
---
# <a name="datetime-xaml-syntax"></a>Sintassi DateTime XAML
Alcuni controlli, ad esempio <xref:System.Windows.Controls.Calendar> e <xref:System.Windows.Controls.DatePicker>, dispongono di proprietà che utilizzano <xref:System.DateTime> il tipo. Anche se una data o un'ora iniziale per questi controlli viene in genere specificata nel code-behind in fase di esecuzione, è possibile specificare una data o un'ora iniziale in XAML. Il parser XAML WPF gestisce l'analisi dei <xref:System.DateTime> valori usando una sintassi del testo XAML incorporata. In questo argomento vengono descritte le specifiche della <xref:System.DateTime> sintassi del testo XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Quando usare la sintassi DateTime XAML  
 Impostare le date in XAML non è sempre necessario e può anche non essere appropriato. Ad esempio, è possibile usare la <xref:System.DateTime.Now%2A?displayProperty=nameWithType> proprietà per inizializzare una data in fase di esecuzione oppure è possibile eseguire tutte le regolazioni della data per un calendario nel code-behind in base all'input dell'utente. Esistono tuttavia scenari in cui è possibile che si desideri impostare come hardcoded le date in <xref:System.Windows.Controls.Calendar> un <xref:System.Windows.Controls.DatePicker> oggetto e in un modello di controllo. Per <xref:System.DateTime> questi scenari, è necessario utilizzare la sintassi XAML.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintassi DateTime di XAML è un comportamento nativo  
 <xref:System.DateTime>è una classe definita nelle librerie di classi di base di CLR. A causa del modo in cui le librerie di classi di base sono correlate al resto di CLR, non è <xref:System.ComponentModel.TypeConverterAttribute> possibile applicarle alla classe e usare un convertitore di tipi per elaborare le stringhe da XAML <xref:System.DateTime> e convertirle in nel modello a oggetti di run-time. Non esiste una classe `DateTimeConverter` che fornisce il comportamento di conversione. Il comportamento di conversione descritto in questo argomento è nativo del parser XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Stringhe di formato per la sintassi DateTime XAML  
 È possibile specificare il formato di un <xref:System.DateTime> oggetto con una stringa di formato. Le stringhe di formato formalizzano la sintassi del testo che può essere usata per creare un valore. <xref:System.DateTime>i valori per i controlli WPF esistenti in genere usano solo i componenti <xref:System.DateTime> data di e non i componenti dell'ora.  
  
 Quando si specifica <xref:System.DateTime> un in XAML, è possibile usare qualsiasi stringa di formato in modo interscambiabile.  
  
 È anche possibile usare formati e stringhe di formato non illustrati in maniera specifica in questo argomento. Tecnicamente, il codice XAML per <xref:System.DateTime> qualsiasi valore specificato e quindi analizzato dal parser XAML WPF usa una chiamata interna a <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, quindi è possibile usare qualsiasi stringa accettata da <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> per l'input XAML. Per altre informazioni, vedere <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La sintassi XAML DateTime USA `en-us` sempre <xref:System.Globalization.CultureInfo> come per la conversione nativa. Questo non è influenzato dal <xref:System.Windows.FrameworkElement.Language%2A> valore o `xml:lang` dal valore in XAML, perché la conversione del tipo a livello di attributo XAML agisce senza tale contesto. Non tentare di interpolare le stringhe di formato mostrate qui a causa di variazioni relative alla lingua, come l'ordine di visualizzazione di giorno e mese. Le stringhe di formato mostrate qui sono le stringhe di formato esatte usate durante l'analisi del codice XAML indipendentemente dalle altre impostazioni cultura.  
  
 Le sezioni seguenti descrivono alcune delle stringhe <xref:System.DateTime> di formato comuni.  
  
### <a name="short-date-pattern-d"></a>Schema di data breve ("d")  
 Di seguito viene illustrato il formato di data breve <xref:System.DateTime> per un in XAML:  
  
 `M/d/YYYY`  
  
 Questo è il formato più semplice che specifica tutte le informazioni necessarie per gli utilizzi tipici per i controlli WPF e non è influenzato dalle differenze di fuso orario rispetto a un componente relativo all'ora, quindi è consigliato rispetto altri formati.  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente:  
  
 `3/1/2010`  
  
 Per altre informazioni, vedere <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Schema di data/ora ordinabile ("s")  
 Di seguito è illustrato il <xref:System.DateTime> modello ordinabile in XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Schema RFC1123 ("r")  
 Il modello RFC1123 è utile perché potrebbe essere un input di stringa da altri generatori di data che usano il modello RFC1123 per via delle impostazioni cultura invariabili. Di seguito viene illustrato il <xref:System.DateTime> modello RFC1123 in XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Altri formati e modelli  
 Come indicato in precedenza, <xref:System.DateTime> è possibile specificare un oggetto in XAML come qualsiasi stringa accettabile come input per <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Sono inclusi altri formati formalizzati (ad esempio <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) e formati che non sono formalizzati come un particolare <xref:System.Globalization.DateTimeFormatInfo> formato. Ad esempio, il form `YYYY/mm/dd` è accettabile come input per <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Questo argomento non tenta di descrivere tutti i possibili formati che funzionano e invece consiglia il formato di data breve come pratica standard.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
