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
ms.openlocfilehash: ad69c0984a9d8c01ebd2198486cd0f6492a6116e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281505"
---
# <a name="how-to-resolve-ambiguous-times"></a>Procedura: risolvere orari ambigui

Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time). Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:

- Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC. Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.

- Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.

In questo argomento viene illustrato come risolvere un'ora ambigua supponendo che rappresenti l'ora solare del fuso orario.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario

1. Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.

2. Se l'ora è ambigua, sottrarre l'ora dall' <xref:System.TimeSpan> oggetto restituito dalla proprietà del fuso orario <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .

3. Chiamare il `static` `Shared` Metodo (in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare la proprietà del valore di data e ora UTC <xref:System.DateTime.Kind%2A> su <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come convertire un'ora ambigua in ora UTC supponendo che rappresenti l'ora solare del fuso orario locale.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il <xref:System.DateTime> valore passato è ambiguo. Se il valore è ambiguo, il metodo restituisce un <xref:System.DateTime> valore che rappresenta l'ora UTC corrispondente. Il metodo gestisce questa conversione sottraendo il valore della proprietà del fuso orario locale <xref:System.TimeZoneInfo.BaseUtcOffset%2A> dall'ora locale.

In genere, un'ora ambigua viene gestita chiamando il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti che contengono i possibili offset UTC dell'ora ambigua. Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario. La <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà restituisce l'offset tra l'ora UTC e l'ora solare di un fuso orario.

In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà. il fuso orario locale non viene mai assegnato a una variabile oggetto. Si tratta di una procedura consigliata perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida gli oggetti a cui è assegnato il fuso orario locale.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Procedura: consentire agli utenti di risolvere orari ambigui](let-users-resolve-ambiguous-times.md)
