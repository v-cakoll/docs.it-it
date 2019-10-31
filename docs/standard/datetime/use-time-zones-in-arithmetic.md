---
title: "Procedura: utilizzare fusi orari nell'aritmetica di data e ora"
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
ms.openlocfilehash: 1acd53fad6b0ab173f855850353339190ebdd893
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132533"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Procedura: utilizzare fusi orari nell'aritmetica di data e ora

In genere, quando si eseguono operazioni aritmetiche di data e ora usando <xref:System.DateTime> o <xref:System.DateTimeOffset> valori, il risultato non riflette alcuna regola di regolazione del fuso orario. Questo vale anche quando il fuso orario del valore di data e ora è chiaramente identificabile, ad esempio quando la proprietà <xref:System.DateTime.Kind%2A> è impostata su <xref:System.DateTimeKind.Local>. In questo argomento viene illustrato come eseguire operazioni aritmetiche su valori di data e ora appartenenti a un determinato fuso orario. I risultati delle operazioni aritmetiche rifletteranno le regole di rettifica del fuso orario.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Per applicare regole di rettifica ai calcoli aritmetici di data e ora

1. Implementare un metodo per vincolare un valore di data e ora al fuso orario al quale appartiene. Ad esempio, dichiarare una struttura che include sia il valore di data e ora sia il fuso orario al quale appartiene. Nell'esempio seguente viene usato questo approccio per collegare un valore <xref:System.DateTime> al relativo fuso orario.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Convertire un'ora in formato UTC (Coordinated Universal Time) chiamando il metodo <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> o il metodo <xref:System.TimeZoneInfo.ConvertTime%2A>.

3. Eseguire l'operazione aritmetica sull'ora UTC.

4. Converte l'ora da UTC al fuso orario associato all'ora originale chiamando il metodo <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

L'esempio seguente aggiunge due ore e trenta minuti al 9 marzo 2008, alle 1.30 ora solare fuso centrale (CST). La transizione del fuso orario all'ora legale si verifica trenta minuti dopo, alle 2.00 del 9 marzo 2008. Poiché nell'esempio vengono seguiti i quattro passaggi elencati nella sezione precedente, l'orario corretto risultante corrisponderà alle 5.00 del 9 marzo 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

I valori <xref:System.DateTime> e <xref:System.DateTimeOffset> sono dissociati da qualsiasi fuso orario a cui possono appartenere. Per eseguire operazioni aritmetiche di data ora con una modalità che applica automaticamente le regole di rettifica del fuso orario, il fuso orario di appartenenza di qualsiasi valore di data e ora deve essere immediatamente identificabile. Ciò significa che una data e ora e il fuso orario associato devono essere strettamente collegati. Esistono diversi modi per ottenere questo risultato, tra cui i seguenti:

- Presupporre che tutti gli orari usati in un'applicazione appartengano a un determinato fuso orario. Pur essendo appropriato in alcuni casi, questo approccio offre una flessibilità limitata e potenzialmente anche una portabilità limitata.

- Definire un tipo che vincoli in modo stretto una data e ora con il fuso orario associato, includendo entrambi come campi del tipo. Questo approccio viene usato nell'esempio di codice, che definisce una struttura per l'archiviazione della data e ora e del fuso orario in due campi membro.

Nell'esempio viene illustrato come eseguire operazioni aritmetiche sui valori <xref:System.DateTime> in modo che le regole di rettifica del fuso orario vengano applicate al risultato. Tuttavia, i valori <xref:System.DateTimeOffset> possono essere usati altrettanto facilmente. Nell'esempio seguente viene illustrato il modo in cui il codice nell'esempio originale può essere adattato per utilizzare <xref:System.DateTimeOffset> anziché <xref:System.DateTime> valori.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Si noti che se questa aggiunta viene eseguita semplicemente sul valore <xref:System.DateTimeOffset> senza prima convertirlo in ora UTC, il risultato riflette il punto nel tempo corretto, ma il relativo offset non riflette quello del fuso orario designato per quell'ora.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che lo spazio dei nomi <xref:System> venga importato con l'istruzione C# `using` (obbligatoria nel codice).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Esecuzione di operazioni aritmetiche con date e ore](../../../docs/standard/datetime/performing-arithmetic-operations.md)
