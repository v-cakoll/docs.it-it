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
ms.openlocfilehash: ebb07800b2a35f4faf312dc55b8c5679079b4b68
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291409"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale

La <xref:System.TimeZoneInfo> classe fornisce due proprietà, <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A> , che consentono al codice di accedere agli oggetti predefiniti del fuso orario. In questo argomento viene illustrato come accedere agli oggetti <xref:System.TimeZoneInfo> restituiti da tali proprietà.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Per accedere all'oggetto TimeZoneInfo dell'ora UTC (Coordinated Universal Time)

1. Utilizzare la `static` `Shared` Proprietà (in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per accedere all'ora UTC (Coordinated Universal Time).

2. Anziché assegnare l' <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere all'ora UTC (Coordinated Universal Time) tramite la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Proprietà.

### <a name="to-access-the-local-time-zone"></a>Per accedere al fuso orario locale

1. Utilizzare la `static` `Shared` Proprietà (in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> per accedere al fuso orario del sistema locale.

2. Anziché assegnare l' <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere al fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà.

## <a name="example"></a>Esempio

Nel codice seguente vengono utilizzate le proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> e <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per convertire un orario del fuso orario standard degli Stati Uniti e Canada orientale, nonché per visualizzare il nome del fuso orario nella console.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

È necessario accedere sempre al fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà anziché assegnare il fuso orario locale a una <xref:System.TimeZoneInfo> variabile oggetto. Analogamente, è consigliabile accedere sempre all'ora UTC (Coordinated Universal Time) tramite la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà anziché assegnare la zona UTC a una <xref:System.TimeZoneInfo> variabile oggetto. In questo modo si impedisce <xref:System.TimeZoneInfo> che la variabile oggetto venga invalidata da una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md)
- [Procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md)
