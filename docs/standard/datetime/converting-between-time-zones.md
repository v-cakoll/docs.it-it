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
ms.openlocfilehash: 0c77832a4c578ddb2c8a427b133e53ab4ab5c5e3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080621"
---
# <a name="converting-times-between-time-zones"></a>Conversione degli orari tra fusi orari

La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore. Un'applicazione non è più possibile presupporre che tutte le volte in cui può essere espresso nell'ora locale, ovvero il tempo disponibile dal <xref:System.DateTime> struttura. Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale. Questo argomento viene illustrato come convertire gli orari da un fuso orario a un altro, nonché come convertire <xref:System.DateTimeOffset> valori che dipendono dal fuso orario.

## <a name="converting-to-coordinated-universal-time"></a>Conversione nel formato UTC

UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico. I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC. L'ora espressa in UTC è quindi indipendente dal fuso orario. L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante. (Per informazioni dettagliate e altre procedure consigliate sull'utilizzo di date e ore, vedere [scrittura di codice le procedure consigliate tramite DateTime in .NET Framework](https://msdn.microsoft.com/library/ms973825.aspx).) La conversione di singoli fusi orari in ore UTC semplifica i confronti tra gli orari.

> [!NOTE]
> È anche possibile serializzare un <xref:System.DateTimeOffset> struttura per rappresentare in modo non ambiguo un singolo punto nel tempo. Poiché <xref:System.DateTimeOffset> oggetti archiviare un valore di data e ora insieme all'offset dall'ora UTC, rappresentano sempre un determinato punto nel tempo in relazione all'ora UTC.

Il modo più semplice per convertire un orario in ora UTC è chiamare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> (metodo). La conversione esatta eseguita dal metodo dipende dal valore della `dateTime` del parametro <xref:System.DateTime.Kind%2A> proprietà, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Converte l'ora locale in ora UTC.                                                    |
| `DateTimeKind.Unspecified` | Presuppone che il parametro `dateTime` sia l'ora locale e converte l'ora locale in ora UTC. |
| `DateTimeKind.Utc`         | Restituisce il parametro `dateTime` invariato.                                    |

Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> Il <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> metodo non comporta necessariamente risultati identici per il <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> e <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> metodi. Se il sistema host locale del fuso orario include più regole di regolazione, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> applica la regola appropriata in una determinata data e ora. Gli altri due metodi vengono sempre applicati alla regola di modifica più recente.

Se il valore di data e ora non rappresenta l'ora locale o UTC, il <xref:System.DateTime.ToUniversalTime%2A> metodo restituirà probabilmente un risultato errato. Tuttavia, è possibile usare il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire la data e ora da un fuso orario specificato. (Per informazioni dettagliate sul recupero di un <xref:System.TimeZoneInfo> oggetto che rappresenta il fuso orario di destinazione, vedere [ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Il codice seguente usa il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire l'ora solare fuso orientale in ora UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Si noti che questo metodo genera un' <xref:System.ArgumentException> se il <xref:System.DateTime> dell'oggetto <xref:System.DateTime.Kind%2A> proprietà e il fuso orario non corrispondono. Una mancata corrispondenza si verifica se il <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> ma il <xref:System.TimeZoneInfo> oggetto non rappresenta il fuso orario locale, o se il <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> ma la <xref:System.TimeZoneInfo> oggetto non è uguale <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Tutti questi metodi accettano <xref:System.DateTime> i valori come parametri e restituiscono un <xref:System.DateTime> valore. Per la <xref:System.DateTimeOffset> valori, il <xref:System.DateTimeOffset> struttura ha un <xref:System.DateTimeOffset.ToUniversalTime%2A> al metodo che converte data e ora dell'istanza corrente in ora UTC dell'istanza. L'esempio seguente chiama il <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo per convertire un'ora locale e diversi altri orari a Coordinated Universal Time (UTC).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversione dell'ora UTC in un determinato fuso orario

Per convertire l'ora UTC nell'ora locale, vedere la sezione "conversione UTC nell'ora locale" di seguito. Per convertire l'ora UTC nell'ora di qualsiasi fuso orario designato, chiamare il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> (metodo). Questo metodo accetta due parametri:

* L'ora UTC da convertire. Questo valore deve essere un <xref:System.DateTime> valore la cui proprietà <xref:System.DateTime.Kind%2A> è impostata su `Unspecified` o `Utc`.

* Il fuso orario nel quale convertire l'ora UTC.

Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversione dell'ora UTC nell'ora locale

Per convertire l'ora UTC nell'ora locale, chiamare il <xref:System.DateTime.ToLocalTime%2A> metodo del <xref:System.DateTime> oggetto la cui ora da convertire. Il comportamento esatto del metodo dipende dal valore dell'oggetto <xref:System.DateTime.Kind%2A> proprietà, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Restituisce il <xref:System.DateTime> valore non modificato.                                      |
| `DateTimeKind.Unspecified` | Si presuppone che il <xref:System.DateTime> valore sia UTC e converte l'ora UTC nell'ora locale. |
| `DateTimeKind.Utc`         | Converte il <xref:System.DateTime> valore nell'ora locale.                                 |

> [!NOTE]
> Il <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> metodo si comporta in modo identico al `DateTime.ToLocalTime` (metodo). Bastano un singolo parametro, ovvero il valore di data e ora da convertire.

È anche possibile convertire l'ora in un determinato fuso orario all'ora locale usando il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> (metodo). Questa tecnica viene illustrata nella sezione successiva.

## <a name="converting-between-any-two-time-zones"></a>Conversione tra due fusi orari

È possibile convertire tra due fusi orari usando uno dei due seguenti `static` (`Shared` in Visual Basic) i metodi del <xref:System.TimeZoneInfo> classe:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  Parametri di questo metodo sono il valore di data e ora da convertire, un `TimeZoneInfo` oggetto che rappresenta il fuso orario del valore data e ora, e un `TimeZoneInfo` oggetto che rappresenta il fuso orario per convertire il valore data e ora.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Parametri di questo metodo sono la data e il valore di ora da convertire, l'identificatore del fuso orario del valore di ora e la data e l'identificatore del fuso orario per convertire il valore data e ora.

Entrambi i metodi richiedono che il <xref:System.DateTime.Kind%2A> proprietà del valore di data e ora da convertire e <xref:System.TimeZoneInfo> identificatore del fuso orario o di oggetto che rappresenta il fuso orario corrispondano tra loro. In caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. Ad esempio, se il `Kind` è di proprietà del valore di data e ora `DateTimeKind.Local`, viene generata un'eccezione se il `TimeZoneInfo` non è uguale all'oggetto passato come parametro al metodo `TimeZoneInfo.Local`. Viene inoltre generata un'eccezione se l'identificatore passato come parametro al metodo non è uguale a `TimeZoneInfo.Local.Id`.

L'esempio seguente usa il <xref:System.TimeZoneInfo.ConvertTime%2A> metodo la conversione dall'ora solare Hawaii all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversione dei valori DateTimeOffset

I valori di data e l'ora rappresentati da <xref:System.DateTimeOffset> oggetti non sono completamente dal fuso orario poiché l'oggetto viene dissociato dal proprio fuso orario al momento, viene creata un'istanza. In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari. Per eseguire questa conversione, è possibile chiamare l'istanza corrente <xref:System.DateTimeOffset.ToOffset%2A> (metodo). L'unico parametro del metodo è l'offset del nuovo valore data e ora che il metodo deve restituire.

Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario Ora solare del Pacifico (Stati Uniti).

Il <xref:System.TimeZoneInfo> classe include anche un overload del <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo che esegue le conversioni di fusi orari con <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> valori. I parametri del metodo sono un <xref:System.DateTimeOffset> un riferimento al fuso orario in cui è necessario convertire l'ora e valore. La chiamata al metodo restituisce un <xref:System.DateTimeOffset> valore. Ad esempio, il `ReturnTimeOnServer` metodo nell'esempio precedente potrebbe essere riscritto come indicato di seguito per chiamare il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> (metodo).

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vedere anche

* <xref:System.TimeZoneInfo>
* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
* [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
