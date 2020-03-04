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
ms.openlocfilehash: fbb59dbe364763209f44a4e2241d1d5275036c40
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156023"
---
# <a name="converting-times-between-time-zones"></a>Conversione degli orari tra fusi orari

La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore. Un'applicazione non può più presupporre che tutti gli orari possano essere espressi nell'ora locale, ovvero il tempo disponibile dalla struttura <xref:System.DateTime>. Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale. In questo argomento viene illustrato come convertire gli orari da un fuso orario a un altro, nonché come convertire <xref:System.DateTimeOffset> valori con una conoscenza limitata del fuso orario.

## <a name="converting-to-coordinated-universal-time"></a>Conversione nel formato UTC

UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico. I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC. L'ora espressa in UTC è quindi indipendente dal fuso orario. L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante. Per informazioni dettagliate e altre procedure consigliate che usano date e ore, vedere la pagina relativa alle procedure consigliate [di codifica usando DateTime nel .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)). La conversione di singoli fusi orari nell'ora UTC rende più semplice confronti temporali.

> [!NOTE]
> È anche possibile serializzare una struttura di <xref:System.DateTimeOffset> per rappresentare in modo non ambiguo un singolo momento. Poiché gli oggetti <xref:System.DateTimeOffset> archiviano un valore di data e ora insieme all'offset rispetto all'ora UTC, rappresentano sempre un particolare punto nel tempo in relazione all'ora UTC.

Il modo più semplice per convertire un'ora in ora UTC consiste nel chiamare il metodo `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>. La conversione esatta eseguita dal metodo dipende dal valore della proprietà <xref:System.DateTime.Kind%2A> del `dateTime` parametro, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Converte l'ora locale in ora UTC.                                                    |
| `DateTimeKind.Unspecified` | Presuppone che il parametro `dateTime` sia l'ora locale e converte l'ora locale in ora UTC. |
| `DateTimeKind.Utc`         | Restituisce il parametro `dateTime` invariato.                                    |

Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Se il valore di data e ora non rappresenta l'ora locale o l'ora UTC, il metodo <xref:System.DateTime.ToUniversalTime%2A> restituirà probabilmente un risultato errato. Tuttavia, è possibile usare il metodo <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> per convertire la data e l'ora da un fuso orario specificato. Per informazioni dettagliate sul recupero di un oggetto <xref:System.TimeZoneInfo> che rappresenta il fuso orario di destinazione, vedere [ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md). Il codice seguente usa il metodo <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> per convertire l'ora solare fuso orientale in ora UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Si noti che questo metodo genera un'<xref:System.ArgumentException> se la proprietà <xref:System.DateTime.Kind%2A> dell'oggetto <xref:System.DateTime> e il fuso orario non corrispondono. Si verifica una mancata corrispondenza se la proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> ma l'oggetto <xref:System.TimeZoneInfo> non rappresenta il fuso orario locale oppure se la proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> ma l'oggetto <xref:System.TimeZoneInfo> non è uguale <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Tutti questi metodi accettano <xref:System.DateTime> valori come parametri e restituiscono un valore <xref:System.DateTime>. Per <xref:System.DateTimeOffset> valori, la struttura <xref:System.DateTimeOffset> dispone di un metodo di istanza <xref:System.DateTimeOffset.ToUniversalTime%2A> che converte la data e l'ora dell'istanza corrente in ora UTC. Nell'esempio seguente viene chiamato il metodo <xref:System.DateTimeOffset.ToUniversalTime%2A> per convertire un'ora locale e diverse altre volte nell'ora UTC (Coordinated Universal Time).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversione dell'ora UTC in un determinato fuso orario

Per convertire l'ora UTC nell'ora locale, vedere la sezione "conversione dell'ora UTC nell'ora locale" riportata di seguito. Per convertire l'ora UTC nell'ora di qualsiasi fuso orario designato, chiamare il metodo <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>. Il metodo accetta due parametri:

- L'ora UTC da convertire. Deve essere un valore <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è impostata su `Unspecified` o `Utc`.

- Il fuso orario nel quale convertire l'ora UTC.

Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversione dell'ora UTC nell'ora locale

Per convertire l'ora UTC nell'ora locale, chiamare il metodo di <xref:System.DateTime.ToLocalTime%2A> dell'oggetto <xref:System.DateTime> di cui si desidera convertire il tempo. Il comportamento esatto del metodo dipende dal valore della proprietà <xref:System.DateTime.Kind%2A> dell'oggetto, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Restituisce il valore <xref:System.DateTime> invariato.                                      |
| `DateTimeKind.Unspecified` | Presuppone che il valore <xref:System.DateTime> sia UTC e converte l'ora UTC nell'ora locale. |
| `DateTimeKind.Utc`         | Converte il valore <xref:System.DateTime> nell'ora locale.                                 |

> [!NOTE]
> Il metodo <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> si comporta in modo identico al metodo `DateTime.ToLocalTime`. Accetta un solo parametro, ovvero il valore di data e ora da convertire.

È anche possibile convertire l'ora in un qualsiasi fuso orario designato in un'ora locale usando il `static` metodo (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType>. Questa tecnica è illustrata nella sezione successiva.

## <a name="converting-between-any-two-time-zones"></a>Conversione tra due fusi orari

È possibile eseguire la conversione tra due fusi orari usando uno dei due metodi di `static` (`Shared` in Visual Basic) seguenti della classe <xref:System.TimeZoneInfo>:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire, un `TimeZoneInfo` oggetto che rappresenta il fuso orario del valore di data e ora e un oggetto `TimeZoneInfo` che rappresenta il fuso orario in cui convertire il valore di data e ora.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire, l'identificatore del fuso orario del valore di data e ora e l'identificatore del fuso orario in cui convertire il valore di data e ora.

Entrambi i metodi richiedono che la proprietà <xref:System.DateTime.Kind%2A> del valore di data e ora da convertire e l'oggetto <xref:System.TimeZoneInfo> o l'identificatore del fuso orario che rappresenta il relativo fuso orario corrispondano tra loro. In caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. Se, ad esempio, la proprietà `Kind` del valore di data e ora è `DateTimeKind.Local`, viene generata un'eccezione se l'oggetto `TimeZoneInfo` passato come parametro al metodo non è uguale a `TimeZoneInfo.Local`. Un'eccezione viene generata anche se l'identificatore passato come parametro al metodo non è uguale a `TimeZoneInfo.Local.Id`.

Nell'esempio seguente viene usato il metodo <xref:System.TimeZoneInfo.ConvertTime%2A> per eseguire la conversione dall'ora solare hawaiana all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversione dei valori DateTimeOffset

I valori di data e ora rappresentati dagli oggetti <xref:System.DateTimeOffset> non sono completamente compatibili con il fuso orario perché l'oggetto è stato dissociato dal fuso orario nel momento in cui viene creata un'istanza. In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari. Per eseguire questa conversione, è possibile chiamare il metodo di <xref:System.DateTimeOffset.ToOffset%2A> dell'istanza corrente. L'unico parametro del metodo è l'offset del nuovo valore di data e ora che il metodo deve restituire.

Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]

Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario standard del Pacifico (Stati Uniti).

La classe <xref:System.TimeZoneInfo> include anche un overload del metodo <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> che esegue le conversioni del fuso orario con valori di <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>. I parametri del metodo sono un valore <xref:System.DateTimeOffset> e un riferimento al fuso orario in cui deve essere convertita l'ora. La chiamata al metodo restituisce un valore <xref:System.DateTimeOffset>. Ad esempio, il metodo `ReturnTimeOnServer` nell'esempio precedente potrebbe essere riscritto come segue per chiamare il metodo <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.TimeZoneInfo>
- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
