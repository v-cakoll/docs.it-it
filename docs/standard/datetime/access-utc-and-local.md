---
title: "Procedura: accedere agli oggetti UTC e l'ora locale zona predefiniti"
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f074e6f6d9b11cc7d7405adced3a4523a31676fa
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086913"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Procedura: accedere agli oggetti UTC e l'ora locale zona predefiniti

Il <xref:System.TimeZoneInfo> classe fornisce due proprietà, <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A>, che forniscono il codice di accesso agli oggetti fuso orario predefinito. In questo argomento viene illustrato come accedere agli oggetti <xref:System.TimeZoneInfo> restituiti da tali proprietà.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Per accedere all'oggetto TimeZoneInfo dell'ora UTC (Coordinated Universal Time)

1. Usare la `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà a cui accedere Coordinated Universal Time.

2. Invece di assegnare il <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere ora UTC usando la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà.

### <a name="to-access-the-local-time-zone"></a>Per accedere al fuso orario locale

1. Usare la `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà per accedere al fuso orario di sistema locale.

2. Invece di assegnare il <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere al fuso orario locale usando il <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà.

## <a name="example"></a>Esempio

Nel codice seguente vengono utilizzate le proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> e <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per convertire un orario del fuso orario standard degli Stati Uniti e Canada orientale, nonché per visualizzare il nome del fuso orario nella console.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

È necessario accedere sempre al fuso orario locale usando il <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà anziché assegnare l'ora locale della zona per una <xref:System.TimeZoneInfo> variabile oggetto. Analogamente, è necessario accedere sempre ora UTC usando la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà anziché assegnare l'ora UTC di zona per una <xref:System.TimeZoneInfo> variabile oggetto. Ciò impedisce che il <xref:System.TimeZoneInfo> variabile oggetto venga invalidata da una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> (metodo).

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Aggiungere un riferimento a DLL al progetto.

* Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (obbligatorio nel codice c#).

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
* [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
* [Procedura: Creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
