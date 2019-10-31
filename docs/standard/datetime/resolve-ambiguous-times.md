---
title: 'Procedura: risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122254"
---
# <a name="how-to-resolve-ambiguous-times"></a>Procedura: risolvere orari ambigui

Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time). Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:

- Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC. Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.

- Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.

In questo argomento viene illustrato come risolvere un'ora ambigua supponendo che rappresenti l'ora solare del fuso orario.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario

1. Chiamare il metodo <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> per determinare se l'ora è ambigua.

2. Se l'ora è ambigua, sottrarre l'ora dall'oggetto <xref:System.TimeSpan> restituito dalla proprietà <xref:System.TimeZoneInfo.BaseUtcOffset%2A> del fuso orario.

3. Chiamare il metodo `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare la proprietà <xref:System.DateTime.Kind%2A> del valore di data e ora UTC su <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come convertire un'ora ambigua in ora UTC supponendo che rappresenti l'ora solare del fuso orario locale.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il valore <xref:System.DateTime> passato è ambiguo. Se il valore è ambiguo, il metodo restituisce un <xref:System.DateTime> valore che rappresenta l'ora UTC corrispondente. Il metodo gestisce questa conversione sottraendo il valore della proprietà <xref:System.TimeZoneInfo.BaseUtcOffset%2A> del fuso orario locale dall'ora locale.

In genere, un'ora ambigua viene gestita chiamando il metodo <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> per recuperare una matrice di <xref:System.TimeSpan> oggetti che contengono gli offset UTC possibili dell'ora ambigua. Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario. La proprietà <xref:System.TimeZoneInfo.BaseUtcOffset%2A> restituisce l'offset tra l'ora UTC e l'ora solare di un fuso orario.

In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>; il fuso orario locale non viene mai assegnato a una variabile oggetto. Si tratta di una procedura consigliata perché una chiamata al metodo <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> invalida gli oggetti a cui è assegnato il fuso orario locale.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo spazio dei nomi <xref:System> venga importato con l'istruzione C# `using` (obbligatoria nel codice).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Consentire agli utenti di risolvere orari ambigui](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
