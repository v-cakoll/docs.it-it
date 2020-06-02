---
title: 'Procedura: consentire agli utenti di risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: ac723738d80a2f686a5fcaf279cec791b3c58619
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281583"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>Procedura: consentire agli utenti di risolvere orari ambigui

Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time). Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:

- Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.

- Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC. Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.

In questo argomento viene illustrato come consentire a un utente di risolvere un'ora ambigua.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>Consentire a un utente di risolvere orari ambigui

1. Ottenere l'input di data e ora dall'utente.

2. Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.

3. Se l'ora è ambigua, chiamare il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti. Ogni elemento nella matrice contiene un offset UTC a cui è possibile eseguire il mapping dell'ora ambigua.

4. Consentire all'utente di selezionare l'offset desiderato.

5. Ottenere la data e l'ora UTC sottraendo dall'ora locale l'offset selezionato dall'utente.

6. Chiamare il `static` `Shared` Metodo (in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare la proprietà del valore di data e ora UTC <xref:System.DateTime.Kind%2A> su <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Esempio

Nell'esempio seguente si richiede all'utente di immettere una data e l'ora e, se è ambigua, si consente all'utente di selezionare l'ora UTC alla quale è associata l'ora ambigua.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

Il nucleo del codice di esempio usa una matrice di <xref:System.TimeSpan> oggetti per indicare possibili offset dell'ora ambigua dall'ora UTC. Tuttavia, questi offset probabilmente non sono significativi per l'utente. Per chiarire il significato degli offset, il codice indica anche se un offset rappresenta l'ora solare o l'ora legale del fuso orario locale. Il codice determina il tempo standard e l'ora legale confrontando l'offset con il valore della <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Proprietà. Questa proprietà indica la differenza tra l'ora solare del fuso orario corrente e l'ora UTC.

In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà. il fuso orario locale non viene mai assegnato a una variabile oggetto. Si tratta di una procedura consigliata perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida gli oggetti a cui è assegnato il fuso orario locale.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Procedura: risolvere orari ambigui](resolve-ambiguous-times.md)
