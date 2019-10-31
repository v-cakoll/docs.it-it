---
title: "Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale"
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132597"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale

La classe <xref:System.TimeZoneInfo> fornisce due proprietà, <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A>, che consentono al codice di accedere agli oggetti predefiniti del fuso orario. In questo argomento viene illustrato come accedere agli oggetti <xref:System.TimeZoneInfo> restituiti da tali proprietà.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Per accedere all'oggetto TimeZoneInfo dell'ora UTC (Coordinated Universal Time)

1. Utilizzare la proprietà `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per accedere all'ora UTC (Coordinated Universal Time).

2. Anziché assegnare l'oggetto <xref:System.TimeZoneInfo> restituito dalla proprietà a una variabile oggetto, continuare ad accedere all'ora UTC (Coordinated Universal Time) tramite la proprietà <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.

### <a name="to-access-the-local-time-zone"></a>Per accedere al fuso orario locale

1. Utilizzare la proprietà `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> per accedere al fuso orario del sistema locale.

2. Anziché assegnare l'oggetto <xref:System.TimeZoneInfo> restituito dalla proprietà a una variabile oggetto, continuare ad accedere al fuso orario locale tramite la proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Nel codice seguente vengono utilizzate le proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> e <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per convertire un orario del fuso orario standard degli Stati Uniti e Canada orientale, nonché per visualizzare il nome del fuso orario nella console.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

È necessario accedere sempre al fuso orario locale tramite la proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> anziché assegnare il fuso orario locale a una variabile oggetto <xref:System.TimeZoneInfo>. Analogamente, è consigliabile accedere sempre all'ora UTC (Coordinated Universal Time) tramite la proprietà <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> anziché assegnare la zona UTC a una variabile oggetto <xref:System.TimeZoneInfo>. In questo modo si impedisce che la variabile oggetto <xref:System.TimeZoneInfo> venga invalidata da una chiamata al metodo <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo spazio dei nomi <xref:System> venga importato con l'istruzione C# `using` (obbligatoria nel codice).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Procedura: Creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
