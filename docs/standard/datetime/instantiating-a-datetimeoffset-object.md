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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50cc71b62581e1fb9302fe241abf6349afd33f8d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106635"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Creazione di un'istanza di un oggetto DateTimeOffset

La <xref:System.DateTimeOffset> struttura offre diversi modi per creare nuovi <xref:System.DateTimeOffset> valori. Molti di essi corrispondono direttamente ai metodi disponibili per creare istanze dei nuovi <xref:System.DateTime> valori, con miglioramenti che consentono di specificare l'offset del valore di data e ora rispetto all'ora UTC (Coordinated Universal Time). In particolare, è possibile creare un'istanza <xref:System.DateTimeOffset> di un valore nei modi seguenti:

- Utilizzando un valore letterale di data e ora.

- Chiamando un <xref:System.DateTimeOffset> costruttore.

- Convertendo in modo implicito un <xref:System.DateTimeOffset> valore in valore.

- Analizzando la rappresentazione di stringa di una data e dell'ora.

In questo argomento vengono forniti maggiori dettagli ed esempi di codice in cui vengono illustrati questi <xref:System.DateTimeOffset> metodi di creazione di un'istanza di nuovi valori.

## <a name="date-and-time-literals"></a>Valori letterali di data e ora

Per i linguaggi che lo supportano, uno dei modi più comuni per creare un'istanza <xref:System.DateTime> di un valore consiste nel fornire la data e l'ora come valore letterale hardcoded. Il codice di Visual Basic seguente, ad esempio, <xref:System.DateTime> crea un oggetto il cui valore è il 1 gennaio 2008, alle 10:00.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>i valori possono essere inizializzati anche con valori letterali di data e ora quando <xref:System.DateTime> si usano linguaggi che supportano i valori letterali. Il codice Visual Basic seguente, ad esempio, crea <xref:System.DateTimeOffset> un oggetto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Come mostra l'output della console, <xref:System.DateTimeOffset> il valore creato in questo modo viene assegnato all'offset del fuso orario locale. Ciò significa che un <xref:System.DateTimeOffset> valore assegnato usando un valore letterale carattere non identifica un singolo momento se il codice viene eseguito in computer diversi.

## <a name="datetimeoffset-constructors"></a>Costruttori DateTimeOffset

Il <xref:System.DateTimeOffset> tipo definisce sei costruttori. Quattro di esse corrispondono direttamente ai <xref:System.DateTime> costruttori, con un parametro aggiuntivo di tipo <xref:System.TimeSpan> che definisce l'offset di data e ora rispetto all'ora UTC. Questi consentono di definire un <xref:System.DateTimeOffset> valore in base al valore dei singoli componenti di data e ora. Il codice seguente, ad esempio, usa questi quattro costruttori per creare un' <xref:System.DateTimeOffset> istanza di oggetti con valori identici di 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Si noti che, quando il valore dell' <xref:System.DateTimeOffset> oggetto di cui è stata <xref:System.Globalization.PersianCalendar> creata un'istanza usando un oggetto come uno degli argomenti per il relativo costruttore viene visualizzato nella console, viene espresso come data nel calendario gregoriano anziché nel calendario persiano. Per restituire una data utilizzando il calendario persiano, vedere l'esempio nell' <xref:System.Globalization.PersianCalendar> argomento.

Gli altri due costruttori creano un <xref:System.DateTimeOffset> oggetto da un <xref:System.DateTime> valore. Il primo di questi ha un solo parametro, il <xref:System.DateTime> valore da convertire in un <xref:System.DateTimeOffset> valore. L'offset del valore risultante <xref:System.DateTimeOffset> dipende <xref:System.DateTime.Kind%2A> dalla proprietà dell'unico parametro del costruttore. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset viene impostato su un <xref:System.TimeSpan.Zero?displayProperty=nameWithType>valore uguale a. In caso contrario, l'offset viene impostato su un valore uguale a quello del fuso orario locale. Nell'esempio seguente viene illustrato l'utilizzo di questo costruttore per creare un' <xref:System.DateTimeOffset> istanza di oggetti che rappresentano l'ora UTC e il fuso orario locale:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> La chiamata dell'overload del <xref:System.DateTimeOffset> costruttore che dispone di un <xref:System.DateTime> singolo parametro equivale all'esecuzione di una conversione implicita <xref:System.DateTime> di un valore <xref:System.DateTimeOffset> in un valore.

Il secondo costruttore che crea un <xref:System.DateTimeOffset> oggetto da un <xref:System.DateTime> valore ha due parametri: il <xref:System.DateTime> valore da convertire e un <xref:System.TimeSpan> valore che rappresenta l'offset di data e ora rispetto all'ora UTC. Questo valore di offset deve corrispondere alla <xref:System.DateTime.Kind%2A> proprietà del primo parametro del costruttore oppure viene generata <xref:System.ArgumentException> un'eccezione. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, il valore del secondo parametro deve essere <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, il valore del secondo parametro deve essere l'offset del fuso orario del sistema locale. Se la <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset può essere qualsiasi valore valido. Il codice seguente illustra le chiamate a questo costruttore per convertire <xref:System.DateTime> <xref:System.DateTimeOffset> i valori.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversione implicita di tipi

Il <xref:System.DateTimeOffset> tipo supporta una conversione implicita di tipi: <xref:System.DateTime> da un valore <xref:System.DateTimeOffset> a un valore. Una conversione implicita di tipi è una conversione da un tipo in un altro che non richiede un cast esplicito (in C#) o una conversione esplicita (in Visual Basic) e nella quale non vengono perse informazioni. Rende possibile la scrittura di codice come il seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

L'offset del valore risultante <xref:System.DateTimeOffset> dipende <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> dal valore della proprietà. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset viene impostato su un <xref:System.TimeSpan.Zero?displayProperty=nameWithType>valore uguale a. Se il valore è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset viene impostato su un valore uguale a quello del fuso orario locale.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analisi della rappresentazione di stringa di una data e di un'ora

Il <xref:System.DateTimeOffset> tipo supporta quattro metodi che consentono di convertire la rappresentazione di stringa di una data e di un'ora <xref:System.DateTimeOffset> in un valore:

- <xref:System.DateTimeOffset.Parse%2A>, che tenta di convertire la rappresentazione di stringa di una data e di un' <xref:System.DateTimeOffset> ora in un valore e genera un'eccezione se la conversione non riesce.

- <xref:System.DateTimeOffset.TryParse%2A>, che tenta di convertire la rappresentazione di stringa di una data e di un' <xref:System.DateTimeOffset> ora in un `false` valore e restituisce se la conversione non riesce.

- <xref:System.DateTimeOffset.ParseExact%2A>, che tenta di convertire in un <xref:System.DateTimeOffset> valore la rappresentazione di stringa di una data e di un'ora in un formato specificato. Il metodo genera un'eccezione se la conversione non riesce.

- <xref:System.DateTimeOffset.TryParseExact%2A>, che tenta di convertire in un <xref:System.DateTimeOffset> valore la rappresentazione di stringa di una data e di un'ora in un formato specificato. Il metodo restituisce `false` se la conversione non riesce.

Nell'esempio seguente vengono illustrate le chiamate a ognuno di questi quattro metodi di conversione di stringhe <xref:System.DateTimeOffset> per creare un'istanza di un valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
