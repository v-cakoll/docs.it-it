---
title: Conversione degli orari tra fusi orari
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7547f0c2dd3651e478bb52106640a7b4525afc29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578898"
---
# <a name="converting-times-between-time-zones"></a>Conversione degli orari tra fusi orari

La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore. Un'applicazione non è più possibile presupporre che tutte le volte in cui può essere espresso nell'ora locale, che è disponibile il tempo di <xref:System.DateTime> struttura. Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale. Questo argomento viene illustrato come effettuare la conversione da un fuso orario a un altro, nonché come eseguire la conversione <xref:System.DateTimeOffset> valori che dipendono dal fuso orario.

## <a name="converting-to-coordinated-universal-time"></a>Conversione nel formato UTC

UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico. I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC. L'ora espressa in UTC è quindi indipendente dal fuso orario. L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante. (Per informazioni dettagliate e altre procedure consigliate sull'utilizzo di date e ore, vedere [utilizzando DateTime in .NET Framework di procedure consigliate di codifica](https://msdn.microsoft.com/library/ms973825.aspx).) La conversione di singoli fusi orari in ore UTC semplifica i confronti tra gli orari.

> [!NOTE]
> È anche possibile serializzare un <xref:System.DateTimeOffset> struttura per rappresentare in modo non ambiguo un singolo punto nel tempo. Poiché <xref:System.DateTimeOffset> oggetti archiviano un valore di data e ora insieme all'offset dall'ora UTC, rappresentano sempre un determinato punto nel tempo in relazione all'ora UTC.

Il modo più semplice per convertire un'ora nell'ora UTC consiste nel chiamare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> metodo. Il tipo specifico di conversione eseguita dal metodo dipende dal valore del `dateTime` del parametro <xref:System.DateTime.Kind%2A> proprietà, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Converte l'ora locale in ora UTC.                                                    |
| `DateTimeKind.Unspecified` | Presuppone che il parametro `dateTime` sia l'ora locale e converte l'ora locale in ora UTC. |
| `DateTimeKind.Utc`         | Restituisce il parametro `dateTime` invariato.                                    |

Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> Il <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> metodo non comporta necessariamente risultati identici al <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> e <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> metodi. Se il sistema host locale del fuso orario include più regole di regolazione, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> applica la regola appropriata per una particolare data e ora. Gli altri due metodi vengono sempre applicati alla regola di modifica più recente.

Se il valore di data e ora non rappresenta l'ora locale o UTC, la <xref:System.DateTime.ToUniversalTime%2A> metodo restituirà probabilmente un risultato errato. Tuttavia, è possibile utilizzare il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire la data e ora da un fuso orario specificato. (Per informazioni dettagliate sul recupero di un <xref:System.TimeZoneInfo> oggetto che rappresenta il fuso orario di destinazione, vedere [ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Il codice seguente usa il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire l'ora solare fuso orientale in UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Si noti che questo metodo genera un <xref:System.ArgumentException> se il <xref:System.DateTime> dell'oggetto <xref:System.DateTime.Kind%2A> proprietà e il fuso orario non corrispondono. Una mancata corrispondenza si verifica se il <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind?displayProperty=nameWithType> ma la <xref:System.TimeZoneInfo> oggetto non rappresenta il fuso orario locale, o se il <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind?displayProperty=nameWithType> ma la <xref:System.TimeZoneInfo> oggetto non è uguale <xref:System.DateTimeKind?displayProperty=nameWithType>.

Tutti questi metodi accettano <xref:System.DateTime> valori come parametri e restituiscono un <xref:System.DateTime> valore. Per <xref:System.DateTimeOffset> valori, il <xref:System.DateTimeOffset> struttura dispone di un <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo che converte la data e l'ora dell'istanza corrente nell'ora UTC di istanza. L'esempio seguente chiama il <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo per convertire un'ora locale e diversi altri orari Coordinated Universal Time (UTC).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversione dell'ora UTC in un determinato fuso orario

Per convertire l'ora UTC in ora locale, vedere la sezione "conversione UTC nell'ora locale" che segue. Per convertire l'ora UTC per il tempo in qualsiasi fuso orario designato, chiamare il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> metodo. Questo metodo accetta due parametri:

* L'ora UTC da convertire. Questo valore deve essere un <xref:System.DateTime> il cui valore <xref:System.DateTime.Kind%2A> è impostata su `Unspecified` o `Utc`.

* Il fuso orario nel quale convertire l'ora UTC.

Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversione dell'ora UTC nell'ora locale

Per convertire l'ora UTC in ora locale, chiamare il <xref:System.DateTime.ToLocalTime%2A> metodo il <xref:System.DateTime> oggetto il cui tempo di cui si desidera convertire. Il comportamento del metodo esatto dipende dal valore dell'oggetto <xref:System.DateTime.Kind%2A> proprietà, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Restituisce il <xref:System.DateTime> valore invariato.                                      |
| `DateTimeKind.Unspecified` | Si presuppone che il <xref:System.DateTime> valore sia l'ora UTC e converte l'ora UTC in ora locale. |
| `DateTimeKind.Utc`         | Converte il <xref:System.DateTime> valore nell'ora locale.                                 |

> [!NOTE]
> Il <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> metodo funziona in modo identico al `DateTime.ToLocalTime` metodo. Accetta un parametro singolo, che corrisponde al valore di data e ora da convertire.

È anche possibile convertire l'ora in un determinato fuso orario locale utilizzando il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> metodo. Questa tecnica è illustrata nella sezione successiva.

## <a name="converting-between-any-two-time-zones"></a>Conversione tra due fusi orari

È possibile convertire tra due fusi orari utilizzando uno dei due seguenti `static` (`Shared` in Visual Basic) metodi di <xref:System.TimeZoneInfo> classe:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  Parametri di questo metodo sono il valore di data e ora da convertire un `TimeZoneInfo` oggetto che rappresenta il fuso orario del valore di data e ora, e un `TimeZoneInfo` oggetto che rappresenta il fuso orario per convertire il valore data e ora.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Parametri di questo metodo sono la data e il valore di ora da convertire, l'identificatore della data e fuso orario del valore di ora e l'identificatore del fuso orario per convertire il valore data e ora.

Entrambi i metodi richiedono che il <xref:System.DateTime.Kind%2A> proprietà del valore di data e ora da convertire e <xref:System.TimeZoneInfo> identificatore di fuso orario o di oggetto che rappresenta il fuso orario corrispondono uno a altro. In caso contrario, un <xref:System.ArgumentException> viene generata un'eccezione. Ad esempio, se il `Kind` è di proprietà del valore di data e ora `DateTimeKind.Local`, viene generata un'eccezione se il `TimeZoneInfo` oggetto passato come parametro al metodo non è uguale a `TimeZoneInfo.Local`. Viene inoltre generata un'eccezione se l'identificatore passato come parametro al metodo non è uguale a `TimeZoneInfo.Local.Id`.

L'esempio seguente usa il <xref:System.TimeZoneInfo.ConvertTime%2A> metodo per la conversione dall'ora solare Hawaii all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversione dei valori DateTimeOffset

I valori di data e l'ora rappresentati da <xref:System.DateTimeOffset> oggetti non sono completamente fuso orario poiché l'oggetto verrà dissociato dal proprio fuso orario al momento ne viene creata un'istanza. In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari. Per eseguire questa conversione, è possibile chiamare l'istanza corrente <xref:System.DateTimeOffset.ToOffset%2A> metodo. L'unico parametro del metodo è l'offset del nuovo valore data e ora che il metodo deve restituire.

Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario Ora solare del Pacifico (Stati Uniti).

Il <xref:System.TimeZoneInfo> include anche un overload di <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo che esegue le conversioni di fuso orario con <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> valori. I parametri del metodo sono un <xref:System.DateTimeOffset> valore e un riferimento al fuso orario in cui è necessario convertire l'ora. La chiamata al metodo restituisce un <xref:System.DateTimeOffset> valore. Ad esempio, il `ReturnTimeOnServer` metodo nell'esempio precedente potrebbe essere riscritto come indicato di seguito per chiamare il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> metodo.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vedere anche

<xref:System.TimeZoneInfo>
[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
