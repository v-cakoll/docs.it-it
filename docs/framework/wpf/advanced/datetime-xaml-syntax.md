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
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186322"
---
# <a name="datetime-xaml-syntax"></a>Sintassi DateTime XAML
Alcuni controlli, <xref:System.Windows.Controls.Calendar> ad <xref:System.Windows.Controls.DatePicker>esempio e , <xref:System.DateTime> dispongono di proprietà che utilizzano il tipo. Anche se una data o un'ora iniziale per questi controlli viene in genere specificata nel code-behind in fase di esecuzione, è possibile specificare una data o un'ora iniziale in XAML. Il parser XAML WPF gestisce l'analisi dei <xref:System.DateTime> valori usando una sintassi di testo XAML incorporata. In questo argomento vengono descritte le specifiche della sintassi del <xref:System.DateTime> testo XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>Quando usare la sintassi DateTime XAML  
 Impostare le date in XAML non è sempre necessario e può anche non essere appropriato. Ad esempio, è <xref:System.DateTime.Now%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per inizializzare una data in fase di esecuzione oppure tutte le regolazioni della data per un calendario nel code-behind in base all'input dell'utente. Tuttavia, esistono scenari in cui è possibile <xref:System.Windows.Controls.Calendar> impostare come hardcoded date in un modello di controllo. <xref:System.Windows.Controls.DatePicker> La <xref:System.DateTime> sintassi XAML deve essere utilizzata per questi scenari.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintassi DateTime di XAML è un comportamento nativo  
 <xref:System.DateTime>è una classe definita nelle librerie di classi base di CLR. A causa del modo in cui le librerie di classi <xref:System.ComponentModel.TypeConverterAttribute> di base sono correlate al resto di CLR, <xref:System.DateTime> non è possibile applicare alla classe e utilizzare un convertitore di tipi per elaborare stringhe da XAML e convertirle nel modello a oggetti del runtime. Non esiste una classe `DateTimeConverter` che fornisce il comportamento di conversione. Il comportamento di conversione descritto in questo argomento è nativo del parser XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>Stringhe di formato per la sintassi DateTime XAML  
 È possibile specificare <xref:System.DateTime> il formato di a con una stringa di formato. Le stringhe di formato formalizzano la sintassi del testo che può essere usata per creare un valore. <xref:System.DateTime>i valori per i controlli WPFWPF <xref:System.DateTime> esistenti in genere utilizzano solo i componenti data di e non i componenti relativi all'ora.  
  
 Quando si <xref:System.DateTime> specifica un in XAML, è possibile usare una qualsiasi delle stringhe di formato in modo intercambiabile.  
  
 È anche possibile usare formati e stringhe di formato non illustrati in maniera specifica in questo argomento. Tecnicamente, il codice <xref:System.DateTime> XAML per qualsiasi valore specificato e quindi analizzato <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>dal parser XAML WPF utilizza <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> una chiamata interna a , pertanto è possibile utilizzare qualsiasi stringa accettata da per l'input XAML. Per altre informazioni, vedere <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La sintassi XAML `en-us` DateTime <xref:System.Globalization.CultureInfo> usa sempre come per la conversione nativa. Questo non è <xref:System.Windows.FrameworkElement.Language%2A> influenzato `xml:lang` dal valore o dal valore nel codice XAML, perché la conversione dei tipi a livello di attributo XAML agisce senza tale contesto. Non tentare di interpolare le stringhe di formato mostrate qui a causa di variazioni relative alla lingua, come l'ordine di visualizzazione di giorno e mese. Le stringhe di formato mostrate qui sono le stringhe di formato esatte usate durante l'analisi del codice XAML indipendentemente dalle altre impostazioni cultura.  
  
 Nelle sezioni seguenti vengono <xref:System.DateTime> descritte alcune delle stringhe di formato comuni.  
  
### <a name="short-date-pattern-d"></a>Schema di data breve ("d")  
 Di seguito viene illustrato il <xref:System.DateTime> formato di data breve per un in XAML:The following shows the short date format for a in XAML:  
  
 `M/d/YYYY`  
  
 Questo è il formato più semplice che specifica tutte le informazioni necessarie per gli utilizzi tipici per i controlli WPF e non è influenzato dalle differenze di fuso orario rispetto a un componente relativo all'ora, quindi è consigliato rispetto altri formati.  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente:  
  
 `3/1/2010`  
  
 Per altre informazioni, vedere <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Schema di data/ora ordinabile ("s")  
 Di seguito viene <xref:System.DateTime> illustrato il modello ordinabile in XAML:The following shows the sortable pattern in XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Schema RFC1123 ("r")  
 Il modello RFC1123 è utile perché potrebbe essere un input di stringa da altri generatori di data che usano il modello RFC1123 per via delle impostazioni cultura invariabili. Di seguito viene illustrato il <xref:System.DateTime> modello RFC1123 in XAML:The following shows the RFC1123 pattern in XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Altri formati e modelli  
 Come indicato in <xref:System.DateTime> precedenza, un in XAML può essere <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>specificato come qualsiasi stringa accettabile come input per . Sono inclusi altri formati formalizzati (ad esempio <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) e <xref:System.Globalization.DateTimeFormatInfo> formati non formalizzati come formato specifico. Ad esempio, `YYYY/mm/dd` il modulo è <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>accettabile come input per . Questo argomento non tenta di descrivere tutti i possibili formati che funzionano e invece consiglia il formato di data breve come pratica standard.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
