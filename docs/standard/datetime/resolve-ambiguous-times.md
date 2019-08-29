---
title: 'Procedura: Risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e98d5d8240492ca30da2825b72277d7a35f97f6
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106775"
---
# <a name="how-to-resolve-ambiguous-times"></a>Procedura: Risolvere orari ambigui

Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time). Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:

- Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC. Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.

- Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.

In questo argomento viene illustrato come risolvere un'ora ambigua supponendo che rappresenti l'ora solare del fuso orario.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario

1. Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.

2. Se l'ora è ambigua, sottrarre l'ora <xref:System.TimeSpan> dall'oggetto restituito dalla <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà del fuso orario.

3. Chiamare il `static` metodo`Shared` (in Visual Basic .NET <xref:System.DateTime.SpecifyKind%2A> ) per <xref:System.DateTime.Kind%2A> impostare la proprietà del valore di data e ora UTC <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>su.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come convertire un'ora ambigua in ora UTC supponendo che rappresenti l'ora solare del fuso orario locale.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

L'esempio è costituito da un `ResolveAmbiguousTime` metodo denominato che determina <xref:System.DateTime> se il valore passato è ambiguo. Se il valore è ambiguo, il metodo restituisce <xref:System.DateTime> un valore che rappresenta l'ora UTC corrispondente. Il metodo gestisce questa conversione sottraendo il valore della <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà del fuso orario locale dall'ora locale.

In genere, un'ora ambigua viene gestita chiamando il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti che contengono i possibili offset UTC dell'ora ambigua. Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario. La <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà restituisce l'offset tra l'ora UTC e l'ora solare di un fuso orario.

In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà. il fuso orario locale non viene mai assegnato a una variabile oggetto. Si tratta di una procedura consigliata perché una chiamata <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> al metodo invalida gli oggetti a cui è assegnato il fuso orario locale.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo <xref:System> spazio dei nomi venga importato con l' C# `using` istruzione (obbligatoria nel codice).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Consentire agli utenti di risolvere orari ambigui](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
