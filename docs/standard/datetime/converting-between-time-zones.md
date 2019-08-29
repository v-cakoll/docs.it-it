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
ms.openlocfilehash: c5b78e3985169954d71b479aa2e8a034f61afc01
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106955"
---
# <a name="converting-times-between-time-zones"></a>Conversione degli orari tra fusi orari

La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore. Un'applicazione non può più presupporre che tutti gli orari possano essere espressi nell'ora locale, ovvero il tempo disponibile <xref:System.DateTime> nella struttura. Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale. In questo argomento viene illustrato come convertire gli orari da un fuso orario a un altro, nonché come convertire <xref:System.DateTimeOffset> i valori con una conoscenza limitata del fuso orario.

## <a name="converting-to-coordinated-universal-time"></a>Conversione nel formato UTC

UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico. I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC. L'ora espressa in UTC è quindi indipendente dal fuso orario. L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante. Per informazioni dettagliate e altre procedure consigliate che usano date e ore, vedere la pagina relativa alle procedure consigliate [di codifica usando DateTime nel .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)). La conversione di singoli fusi orari in ore UTC semplifica i confronti tra gli orari.

> [!NOTE]
> È inoltre possibile serializzare <xref:System.DateTimeOffset> una struttura per rappresentare in modo non ambiguo un singolo momento. Poiché <xref:System.DateTimeOffset> gli oggetti archiviano un valore di data e ora insieme all'offset rispetto all'ora UTC, rappresentano sempre un particolare punto nel tempo in relazione all'ora UTC.

Il modo più semplice per convertire un'ora in ora UTC è chiamare `static` il`Shared` metodo (in <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Visual Basic). La conversione esatta eseguita dal metodo dipende dal valore della `dateTime` <xref:System.DateTime.Kind%2A> proprietà del parametro, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Converte l'ora locale in ora UTC.                                                    |
| `DateTimeKind.Unspecified` | Presuppone che il parametro `dateTime` sia l'ora locale e converte l'ora locale in ora UTC. |
| `DateTimeKind.Utc`         | Restituisce il parametro `dateTime` invariato.                                    |

Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Se il valore di data e ora non rappresenta l'ora locale o l'ora UTC, <xref:System.DateTime.ToUniversalTime%2A> il metodo restituirà probabilmente un risultato errato. Tuttavia, è possibile usare il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire la data e l'ora da un fuso orario specificato. Per informazioni dettagliate sul recupero di un <xref:System.TimeZoneInfo> oggetto che rappresenta il fuso orario di destinazione, vedere [ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md). Il codice seguente usa il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metodo per convertire l'ora solare fuso orientale in ora UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Si noti che questo metodo genera <xref:System.ArgumentException> un'eccezione <xref:System.DateTime> se la <xref:System.DateTime.Kind%2A> proprietà dell'oggetto e il fuso orario non corrispondono. Si verifica una mancata corrispondenza <xref:System.DateTime.Kind%2A> se la <xref:System.DateTimeKind.Local?displayProperty=nameWithType> proprietà è <xref:System.TimeZoneInfo> ma l'oggetto non rappresenta il fuso orario locale oppure se la <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> ma l' <xref:System.TimeZoneInfo> oggetto non è uguale <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>A.

Tutti questi metodi accettano <xref:System.DateTime> valori come parametri e restituiscono un <xref:System.DateTime> valore. Per <xref:System.DateTimeOffset> i valori, <xref:System.DateTimeOffset> la struttura dispone <xref:System.DateTimeOffset.ToUniversalTime%2A> di un metodo di istanza che converte la data e l'ora dell'istanza corrente in ora UTC. Nell'esempio seguente viene chiamato <xref:System.DateTimeOffset.ToUniversalTime%2A> il metodo per convertire un'ora locale e diverse altre volte nell'ora UTC (Coordinated Universal Time).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversione dell'ora UTC in un determinato fuso orario

Per convertire l'ora UTC nell'ora locale, vedere la sezione "conversione dell'ora UTC nell'ora locale" riportata di seguito. Per convertire l'ora UTC nell'ora di qualsiasi fuso orario designato, chiamare il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> metodo. Questo metodo accetta due parametri:

- L'ora UTC da convertire. Deve essere un <xref:System.DateTime> valore la cui <xref:System.DateTime.Kind%2A> proprietà è impostata su `Unspecified` o `Utc`.

- Il fuso orario nel quale convertire l'ora UTC.

Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversione dell'ora UTC nell'ora locale

Per convertire l'ora UTC nell'ora locale, <xref:System.DateTime.ToLocalTime%2A> chiamare il metodo <xref:System.DateTime> dell'oggetto di cui si desidera convertire il tempo. Il comportamento esatto del metodo dipende dal valore della <xref:System.DateTime.Kind%2A> proprietà dell'oggetto, come illustrato nella tabella seguente.

| `DateTime.Kind`            | Conversione                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Restituisce il <xref:System.DateTime> valore invariato.                                      |
| `DateTimeKind.Unspecified` | Presuppone che il <xref:System.DateTime> valore sia UTC e converte l'ora UTC nell'ora locale. |
| `DateTimeKind.Utc`         | Converte il <xref:System.DateTime> valore nell'ora locale.                                 |

> [!NOTE]
> Il <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> metodo si comporta `DateTime.ToLocalTime` in modo identico al metodo. Accetta un solo parametro, ovvero il valore di data e ora da convertire.

È anche possibile convertire l'ora in un qualsiasi fuso orario designato nell'ora locale usando `static` il`Shared` metodo (in <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> Visual Basic). Questa tecnica è illustrata nella sezione successiva.

## <a name="converting-between-any-two-time-zones"></a>Conversione tra due fusi orari

È possibile eseguire la `static` <xref:System.TimeZoneInfo> conversione tra due fusi orari utilizzando uno dei due metodi (`Shared` in Visual Basic) seguenti della classe:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire `TimeZoneInfo` , un oggetto che rappresenta il fuso orario del valore di data e ora e `TimeZoneInfo` un oggetto che rappresenta il fuso orario in cui convertire il valore di data e ora.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  I parametri di questo metodo sono il valore di data e ora da convertire, l'identificatore del fuso orario del valore di data e ora e l'identificatore del fuso orario in cui convertire il valore di data e ora.

Entrambi i metodi richiedono che <xref:System.DateTime.Kind%2A> la proprietà del valore di data e ora da convertire e <xref:System.TimeZoneInfo> l'oggetto o l'identificatore del fuso orario che rappresenta il relativo fuso orario corrispondano tra loro. In caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. Se, ad esempio, `Kind` la proprietà del valore di data e ora `DateTimeKind.Local`è, viene generata un'eccezione se `TimeZoneInfo` l'oggetto passato come parametro al metodo non è uguale a `TimeZoneInfo.Local`. Un'eccezione viene generata anche se l'identificatore passato come parametro al metodo non è uguale a `TimeZoneInfo.Local.Id`.

Nell'esempio seguente viene usato <xref:System.TimeZoneInfo.ConvertTime%2A> il metodo per eseguire la conversione dall'ora solare hawaiana all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversione dei valori DateTimeOffset

I valori di data e ora <xref:System.DateTimeOffset> rappresentati dagli oggetti non sono completamente compatibili con il fuso orario perché l'oggetto è stato dissociato dal fuso orario nel momento in cui viene creata un'istanza. In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari. Per eseguire questa conversione, è possibile chiamare il <xref:System.DateTimeOffset.ToOffset%2A> metodo dell'istanza corrente. L'unico parametro del metodo è l'offset del nuovo valore di data e ora che il metodo deve restituire.

Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario Ora solare del Pacifico (Stati Uniti).

La <xref:System.TimeZoneInfo> classe include anche un overload del metodo <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> che esegue le conversioni del fuso orario con <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> i valori. I parametri del metodo sono un <xref:System.DateTimeOffset> valore e un riferimento al fuso orario in cui deve essere convertita l'ora. La chiamata al metodo restituisce <xref:System.DateTimeOffset> un valore. Ad esempio, il `ReturnTimeOnServer` metodo nell'esempio precedente potrebbe essere riscritto come segue per chiamare il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> metodo.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.TimeZoneInfo>
- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
