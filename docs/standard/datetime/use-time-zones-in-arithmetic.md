---
title: "Procedura: Usare fusi orari nell'aritmetica di data e ora"
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d504aa9ad7d6e4084192a2434ac408e8fa7a041
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588536"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Procedura: Usare fusi orari nell'aritmetica di data e ora

In genere, quando si esegue Data e ora utilizzando aritmetica <xref:System.DateTime> o <xref:System.DateTimeOffset> valori, il risultato non riflette eventuali regole di rettifica del fuso orario. Questo vale anche quando il fuso orario del valore di data e ora è chiaramente identificabile (ad esempio, quando la <xref:System.DateTime.Kind%2A> è impostata su <xref:System.DateTimeKind.Local>). In questo argomento viene illustrato come eseguire operazioni aritmetiche su valori di data e ora appartenenti a un determinato fuso orario. I risultati delle operazioni aritmetiche rifletteranno le regole di rettifica del fuso orario.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Per applicare regole di rettifica ai calcoli aritmetici di data e ora

1. Implementare un metodo per vincolare un valore di data e ora al fuso orario al quale appartiene. Ad esempio, dichiarare una struttura che include sia il valore di data e ora sia il fuso orario al quale appartiene. L'esempio seguente usa questo approccio per collegare un <xref:System.DateTime> valore al proprio fuso orario.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Convertire un'ora per ora Coordinated Universal Time (UTC) chiamando il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodo o il <xref:System.TimeZoneInfo.ConvertTime%2A> (metodo).

3. Eseguire l'operazione aritmetica sull'ora UTC.

4. Convertire l'ora da UTC al fuso orario associato all'ora originale chiamando il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> (metodo).

## <a name="example"></a>Esempio

L'esempio seguente aggiunge due ore e trenta minuti al 9 marzo 2008, alle 1.30 ora solare fuso centrale (CST). La transizione del fuso orario all'ora legale si verifica trenta minuti dopo, alle 2.00 del 9 marzo 2008. Poiché nell'esempio vengono seguiti i quattro passaggi elencati nella sezione precedente, l'orario corretto risultante corrisponderà alle 5.00 del 9 marzo 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Entrambe <xref:System.DateTime> e <xref:System.DateTimeOffset> valori sono dissociati da qualsiasi fuso orario al quale appartengono. Per eseguire operazioni aritmetiche di data ora con una modalità che applica automaticamente le regole di rettifica del fuso orario, il fuso orario di appartenenza di qualsiasi valore di data e ora deve essere immediatamente identificabile. Ciò significa che una data e ora e il fuso orario associato devono essere strettamente collegati. Esistono diversi modi per ottenere questo risultato, tra cui i seguenti:

* Presupporre che tutti gli orari usati in un'applicazione appartengano a un determinato fuso orario. Pur essendo appropriato in alcuni casi, questo approccio offre una flessibilità limitata e potenzialmente anche una portabilità limitata.

* Definire un tipo che vincoli in modo stretto una data e ora con il fuso orario associato, includendo entrambi come campi del tipo. Questo approccio viene usato nell'esempio di codice, che definisce una struttura per l'archiviazione della data e ora e del fuso orario in due campi membro.

Nell'esempio viene illustrato come eseguire operazioni aritmetiche su <xref:System.DateTime> valori in modo che le regole di regolazione fuso orario vengono applicate al risultato. Tuttavia, <xref:System.DateTimeOffset> valori possono essere usati con la stessa semplicità. Nell'esempio seguente viene illustrato come il codice nell'esempio originale potrebbe essere adattato per l'utilizzo <xref:System.DateTimeOffset> invece di <xref:System.DateTime> valori.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Si noti che se questa aggiunta viene eseguita semplicemente il <xref:System.DateTimeOffset> valore senza prima convertirlo a UTC, il risultato riflette il momento esatto in tempo ma l'offset non riflette quello del fuso orario designato per quell'ora.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (obbligatorio nel codice c#).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Esecuzione di operazioni aritmetiche con date e ore](../../../docs/standard/datetime/performing-arithmetic-operations.md)
