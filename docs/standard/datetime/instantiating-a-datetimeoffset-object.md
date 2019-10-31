---
title: Creazione di un'istanza di un oggetto DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
ms.openlocfilehash: 1b1178623258393eab28a7087eb04c47b55a9176
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122316"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Creazione di un'istanza di un oggetto DateTimeOffset

La struttura <xref:System.DateTimeOffset> offre diversi modi per creare nuovi valori <xref:System.DateTimeOffset>. Molti di essi corrispondono direttamente ai metodi disponibili per creare istanze dei nuovi valori di <xref:System.DateTime>, con miglioramenti che consentono di specificare l'offset del valore di data e ora rispetto all'ora UTC (Coordinated Universal Time). In particolare, è possibile creare un'istanza di un valore <xref:System.DateTimeOffset> nei modi seguenti:

- Utilizzando un valore letterale di data e ora.

- Chiamando un costruttore <xref:System.DateTimeOffset>.

- Convertendo in modo implicito un valore in <xref:System.DateTimeOffset> valore.

- Analizzando la rappresentazione di stringa di una data e dell'ora.

In questo argomento vengono forniti maggiori dettagli ed esempi di codice in cui vengono illustrati questi metodi di creazione di un'istanza di nuovi valori di <xref:System.DateTimeOffset>.

## <a name="date-and-time-literals"></a>Valori letterali di data e ora

Per i linguaggi che lo supportano, uno dei modi più comuni per creare un'istanza di un valore di <xref:System.DateTime> consiste nel fornire la data e l'ora come valore letterale hardcoded. Il codice di Visual Basic seguente, ad esempio, crea un oggetto <xref:System.DateTime> il cui valore è il 1 gennaio 2008, alle 10:00.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

è possibile inizializzare i valori di <xref:System.DateTimeOffset> anche usando i valori letterali di data e ora quando si usano linguaggi che supportano <xref:System.DateTime> valori letterali. Il codice Visual Basic seguente, ad esempio, crea un oggetto <xref:System.DateTimeOffset>.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Come mostra l'output della console, il valore <xref:System.DateTimeOffset> creato in questo modo viene assegnato l'offset del fuso orario locale. Ciò significa che un valore <xref:System.DateTimeOffset> assegnato usando un valore letterale carattere non identifica un singolo punto di tempo se il codice viene eseguito in computer diversi.

## <a name="datetimeoffset-constructors"></a>Costruttori DateTimeOffset

Il tipo di <xref:System.DateTimeOffset> definisce sei costruttori. Quattro di esse corrispondono direttamente a costruttori di <xref:System.DateTime>, con un parametro aggiuntivo di tipo <xref:System.TimeSpan> che definisce l'offset di data e ora rispetto all'ora UTC. Che consentono di definire un valore <xref:System.DateTimeOffset> in base al valore dei singoli componenti di data e ora. Il codice seguente, ad esempio, usa questi quattro costruttori per creare un'istanza di oggetti <xref:System.DateTimeOffset> con valori identici di 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Si noti che, quando il valore dell'oggetto <xref:System.DateTimeOffset> di cui è stata creata un'istanza usando un oggetto <xref:System.Globalization.PersianCalendar> come uno degli argomenti per il relativo costruttore viene visualizzato nella console, viene espresso come data nel calendario gregoriano anziché nel calendario persiano. Per restituire una data utilizzando il calendario persiano, vedere l'esempio nell'argomento <xref:System.Globalization.PersianCalendar>.

Gli altri due costruttori creano un oggetto <xref:System.DateTimeOffset> da un valore <xref:System.DateTime>. Il primo ha un solo parametro, il <xref:System.DateTime> valore da convertire in un valore <xref:System.DateTimeOffset>. L'offset del valore di <xref:System.DateTimeOffset> risultante dipende dalla proprietà <xref:System.DateTime.Kind%2A> dell'unico parametro del costruttore. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset viene impostato su un valore uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. In caso contrario, l'offset viene impostato su un valore uguale a quello del fuso orario locale. Nell'esempio seguente viene illustrato l'utilizzo di questo costruttore per creare un'istanza di oggetti <xref:System.DateTimeOffset> che rappresentano l'ora UTC e il fuso orario locale:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> La chiamata dell'overload del costruttore <xref:System.DateTimeOffset> che dispone di un singolo parametro di <xref:System.DateTime> equivale all'esecuzione di una conversione implicita di un valore <xref:System.DateTime> in un valore <xref:System.DateTimeOffset>.

Il secondo costruttore che crea un oggetto <xref:System.DateTimeOffset> da un valore <xref:System.DateTime> dispone di due parametri: il <xref:System.DateTime> valore da convertire e un valore <xref:System.TimeSpan> che rappresenta l'offset di data e ora rispetto all'ora UTC. Questo valore di offset deve corrispondere alla proprietà <xref:System.DateTime.Kind%2A> del primo parametro del costruttore oppure viene generata un'<xref:System.ArgumentException>. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, il valore del secondo parametro deve essere <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, il valore del secondo parametro deve essere l'offset del fuso orario del sistema locale. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset può essere qualsiasi valore valido. Il codice seguente illustra le chiamate a questo costruttore per convertire <xref:System.DateTime> in valori <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversione implicita di tipi

Il tipo di <xref:System.DateTimeOffset> supporta una conversione implicita di tipi: da un valore <xref:System.DateTime> a un valore di <xref:System.DateTimeOffset>. Una conversione implicita di tipi è una conversione da un tipo in un altro che non richiede un cast esplicito (in C#) o una conversione esplicita (in Visual Basic) e nella quale non vengono perse informazioni. Rende possibile la scrittura di codice come il seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

L'offset del valore di <xref:System.DateTimeOffset> risultante dipende dal valore della proprietà <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset viene impostato su un valore uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se il valore è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset viene impostato su un valore uguale a quello del fuso orario locale.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analisi della rappresentazione di stringa di una data e di un'ora

Il tipo di <xref:System.DateTimeOffset> supporta quattro metodi che consentono di convertire la rappresentazione di stringa di una data e di un'ora in un valore <xref:System.DateTimeOffset>:

- <xref:System.DateTimeOffset.Parse%2A>, che tenta di convertire la rappresentazione di stringa di una data e di un'ora in un valore <xref:System.DateTimeOffset> e genera un'eccezione se la conversione non riesce.

- <xref:System.DateTimeOffset.TryParse%2A>, che tenta di convertire la rappresentazione di stringa di una data e di un'ora in un valore <xref:System.DateTimeOffset> e restituisce `false` se la conversione non riesce.

- <xref:System.DateTimeOffset.ParseExact%2A>, che tenta di convertire la rappresentazione di stringa di una data e un'ora in un formato specificato in un valore di <xref:System.DateTimeOffset>. Il metodo genera un'eccezione se la conversione non riesce.

- <xref:System.DateTimeOffset.TryParseExact%2A>, che tenta di convertire la rappresentazione di stringa di una data e un'ora in un formato specificato in un valore di <xref:System.DateTimeOffset>. Il metodo restituisce `false` se la conversione non riesce.

Nell'esempio seguente vengono illustrate le chiamate a ognuno di questi quattro metodi di conversione di stringhe per creare un'istanza di un valore <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
