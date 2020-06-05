---
title: Conversione degli orari tra fusi orari
description: Informazioni su come convertire gli orari tra un fuso orario e un altro in .NET. Impara anche a convertire i valori DateTimeOffset con una conoscenza limitata del fuso orario.
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
ms.openlocfilehash: 7d1984866c5eacdfe21834389b8f0be4caf78fb7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446841"
---
# <a name="converting-times-between-time-zones"></a>Conversione degli orari tra fusi orari

La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore. Un'applicazione non può più presupporre che tutti gli orari possano essere espressi nell'ora locale, ovvero il tempo disponibile nella <xref:System.DateTime> struttura. Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale. In questo argomento viene illustrato come convertire gli orari da un fuso orario a un altro, nonché come convertire <xref:System.DateTimeOffset> i valori con una conoscenza limitata del fuso orario.

## <a name="converting-to-coordinated-universal-time"></a>Conversione nel formato UTC

UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico. I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC. L'ora espressa in UTC è quindi indipendente dal fuso orario. L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante. Per informazioni dettagliate e altre procedure consigliate che usano date e ore, vedere la pagina relativa alle procedure consigliate [di codifica usando DateTime nel .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)). La conversione di singoli fusi orari nell'ora UTC rende più semplice confronti temporali.

> [!NOTE]
> È inoltre possibile serializzare una <xref:System.DateTimeOffset> struttura per rappresentare in modo non ambiguo un singolo momento. Poiché <xref:System.DateTimeOffset> gli oggetti archiviano un valore di data e ora insieme all'offset rispetto all'ora UTC, rappresentano sempre un particolare punto nel tempo in relazione all'ora UTC.

Il modo più semplice per convertire un'ora in ora UTC è chiamare `static` il `Shared` Metodo (in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> . La conversione esatta eseguita dal metodo dipende dal valore della `dateTime` proprietà del parametro <xref:System.DateTime.Kind%2A> , come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Converte l'ora locale in ora UTC.                                                    |
| `DateTimeKind.Unspecified` | Presuppone che il parametro `dateTime` sia l'ora locale e converte l'ora locale in ora UTC. |
| `DateTimeKind.Utc`         | Restituisce il parametro `dateTime` invariato.                                    |

Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Se il valore di data e ora non rappresenta l'ora locale o l'ora UTC, il <xref:System.DateTime.ToUniversalTime%2A> metodo restituirà probabilmente un risultato errato. Tuttavia, è possibile usare il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire la data e l'ora da un fuso orario specificato. Per informazioni dettagliate sul recupero di un <xref:System.TimeZoneInfo> oggetto che rappresenta il fuso orario di destinazione, vedere [ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md). Il codice seguente usa il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire l'ora solare fuso orientale in ora UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Si noti che questo metodo genera un'eccezione <xref:System.ArgumentException> se la <xref:System.DateTime> proprietà dell'oggetto <xref:System.DateTime.Kind%2A> e il fuso orario non corrispondono. Si verifica una mancata corrispondenza se la <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> ma l' <xref:System.TimeZoneInfo> oggetto non rappresenta il fuso orario locale oppure se la <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> ma l' <xref:System.TimeZoneInfo> oggetto <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType> non è uguale A.

Tutti questi metodi accettano <xref:System.DateTime> valori come parametri e restituiscono un <xref:System.DateTime> valore. Per i <xref:System.DateTimeOffset> valori, la <xref:System.DateTimeOffset> struttura dispone di un <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo di istanza che converte la data e l'ora dell'istanza corrente in ora UTC. Nell'esempio seguente viene chiamato il <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo per convertire un'ora locale e diverse altre volte nell'ora UTC (Coordinated Universal Time).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversione dell'ora UTC in un determinato fuso orario

Per convertire l'ora UTC nell'ora locale, vedere la sezione "conversione dell'ora UTC nell'ora locale" riportata di seguito. Per convertire l'ora UTC nell'ora di qualsiasi fuso orario designato, chiamare il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> metodo. Il metodo accetta due parametri:

- L'ora UTC da convertire. Deve essere un <xref:System.DateTime> valore la cui <xref:System.DateTime.Kind%2A> proprietà è impostata su `Unspecified` o `Utc` .

- Il fuso orario nel quale convertire l'ora UTC.

Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversione dell'ora UTC nell'ora locale

Per convertire l'ora UTC nell'ora locale, chiamare il <xref:System.DateTime.ToLocalTime%2A> metodo dell' <xref:System.DateTime> oggetto di cui si desidera convertire il tempo. Il comportamento esatto del metodo dipende dal valore della proprietà dell'oggetto <xref:System.DateTime.Kind%2A> , come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Restituisce il <xref:System.DateTime> valore invariato.                                      |
| `DateTimeKind.Unspecified` | Presuppone che il <xref:System.DateTime> valore sia UTC e converte l'ora UTC nell'ora locale. |
| `DateTimeKind.Utc`         | Converte il <xref:System.DateTime> valore nell'ora locale.                                 |

> [!NOTE]
> Il <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> metodo si comporta in modo identico al `DateTime.ToLocalTime` metodo. Accetta un solo parametro, ovvero il valore di data e ora da convertire.

È anche possibile convertire l'ora in un qualsiasi fuso orario designato nell'ora locale usando `static` il `Shared` Metodo (in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> . Questa tecnica è illustrata nella sezione successiva.

## <a name="converting-between-any-two-time-zones"></a>Conversione tra due fusi orari

È possibile eseguire la conversione tra due fusi orari utilizzando uno dei due `static` `Shared` metodi (in Visual Basic) seguenti della <xref:System.TimeZoneInfo> classe:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire, un `TimeZoneInfo` oggetto che rappresenta il fuso orario del valore di data e ora e un `TimeZoneInfo` oggetto che rappresenta il fuso orario in cui convertire il valore di data e ora.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire, l'identificatore del fuso orario del valore di data e ora e l'identificatore del fuso orario in cui convertire il valore di data e ora.

Entrambi i metodi richiedono che la <xref:System.DateTime.Kind%2A> proprietà del valore di data e ora da convertire e l' <xref:System.TimeZoneInfo> oggetto o l'identificatore del fuso orario che rappresenta il relativo fuso orario corrispondano tra loro. In caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. Se, ad esempio, la `Kind` proprietà del valore di data e ora è `DateTimeKind.Local` , viene generata un'eccezione se l' `TimeZoneInfo` oggetto passato come parametro al metodo non è uguale a `TimeZoneInfo.Local` . Un'eccezione viene generata anche se l'identificatore passato come parametro al metodo non è uguale a `TimeZoneInfo.Local.Id` .

Nell'esempio seguente viene usato il <xref:System.TimeZoneInfo.ConvertTime%2A> metodo per eseguire la conversione dall'ora solare hawaiana all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversione dei valori DateTimeOffset

I valori di data e ora rappresentati dagli <xref:System.DateTimeOffset> oggetti non sono completamente compatibili con il fuso orario perché l'oggetto è stato dissociato dal fuso orario nel momento in cui viene creata un'istanza. In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari. Per eseguire questa conversione, è possibile chiamare il metodo dell'istanza corrente <xref:System.DateTimeOffset.ToOffset%2A> . L'unico parametro del metodo è l'offset del nuovo valore di data e ora che il metodo deve restituire.

Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]

Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario standard del Pacifico (Stati Uniti).

La <xref:System.TimeZoneInfo> classe include anche un overload del <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo che esegue le conversioni del fuso orario con <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> i valori. I parametri del metodo sono un <xref:System.DateTimeOffset> valore e un riferimento al fuso orario in cui deve essere convertita l'ora. La chiamata al metodo restituisce un <xref:System.DateTimeOffset> valore. Ad esempio, il `ReturnTimeOnServer` metodo nell'esempio precedente potrebbe essere riscritto come segue per chiamare il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> metodo.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.TimeZoneInfo>
- [Date, ore e fusi orari](index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md)
