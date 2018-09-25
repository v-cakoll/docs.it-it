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
ms.openlocfilehash: 6d8f4254da256bf2814f66aa62d43204fb302701
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070721"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Creazione di un'istanza di un oggetto DateTimeOffset

Il <xref:System.DateTimeOffset> struttura offre diversi modi per creare nuovi <xref:System.DateTimeOffset> valori. Molti corrispondono direttamente ai metodi disponibili per creare istanze dei nuovi <xref:System.DateTime> valori, con miglioramenti che consentono di specificare il valore di data e ora offset dall'ora Coordinated Universal Time (UTC). In particolare, è possibile creare un'istanza di un <xref:System.DateTimeOffset> valore nei modi seguenti:

* Con una data e ora letterale.

* Chiamando un <xref:System.DateTimeOffset> costruttore.

* Convertendo in modo implicito un valore a <xref:System.DateTimeOffset> valore.

* Analizzando la rappresentazione di stringa di una data e dell'ora.

In questo argomento fornisce maggiori dettagli ed esempi di codice che illustrano questi metodi di un'istanza nuova <xref:System.DateTimeOffset> valori.

## <a name="date-and-time-literals"></a>Valori letterali di data e ora

Per i linguaggi che supportano questa opzione, uno dei modi più comuni per creare un'istanza di un <xref:System.DateTime> valore consiste nel fornire la data e ora come valore letterale hardcoded. Ad esempio, il codice di Visual Basic seguente crea un <xref:System.DateTime> oggetto il cui valore corrisponde al 1 gennaio 2008, alle 10.00.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> i valori possono inoltre essere inizializzati mediante valori letterali di data e ora quando si usano linguaggi che supportano <xref:System.DateTime> valori letterali. Ad esempio, il codice di Visual Basic seguente crea un <xref:System.DateTimeOffset> oggetto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Come illustrato nell'output di console, la <xref:System.DateTimeOffset> valore creato in questo modo viene assegnato l'offset del fuso orario locale. Ciò significa che un <xref:System.DateTimeOffset> valore assegnato usando un valore letterale carattere non identifica un singolo punto di tempo se il codice viene eseguito in computer diversi.

## <a name="datetimeoffset-constructors"></a>Costruttori DateTimeOffset

Il <xref:System.DateTimeOffset> tipo definisce sei costruttori disponibili. Quattro delle quali corrispondono direttamente ai <xref:System.DateTime> costruttori, con un parametro di tipo <xref:System.TimeSpan> che definisce la data e l'offset dell'ora rispetto all'ora UTC. Questi consentono di definire un <xref:System.DateTimeOffset> valore basato sul valore della relativa singoli componenti di data e ora. Ad esempio, il codice seguente Usa queste quattro costruttori per creare un'istanza <xref:System.DateTimeOffset> oggetti con valori identici di 7/1/2008 12:05 + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Si noti che, quando il valore della <xref:System.DateTimeOffset> oggetto creata un'istanza usando un <xref:System.Globalization.PersianCalendar> oggetto come uno degli argomenti nel relativo costruttore viene visualizzato nella console, viene espresso come data del calendario gregoriano anziché persiano. Per restituire una data utilizzando il calendario persiano, vedere l'esempio nel <xref:System.Globalization.PersianCalendar> argomento.

Gli altri due costruttori creano un <xref:System.DateTimeOffset> dell'oggetto da un <xref:System.DateTime> valore. Il primo ha un solo parametro, il <xref:System.DateTime> valore da convertire in un <xref:System.DateTimeOffset> valore. L'offset del valore risultante <xref:System.DateTimeOffset> dipende dal valore di <xref:System.DateTime.Kind%2A> proprietà dell'unico parametro del costruttore. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset è uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. In caso contrario, l'offset viene impostato su un valore uguale a quello del fuso orario locale. Nell'esempio seguente viene illustrato l'utilizzo di questo costruttore per creare un'istanza <xref:System.DateTimeOffset> oggetti che rappresentano il fuso orario locale e UTC:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Chiamare l'overload del <xref:System.DateTimeOffset> costruttore con un singolo <xref:System.DateTime> parametro equivale all'esecuzione di una conversione implicita di un <xref:System.DateTime> valore a un <xref:System.DateTimeOffset> valore.

Il secondo costruttore che crea una <xref:System.DateTimeOffset> dell'oggetto da un <xref:System.DateTime> valore presenta due parametri: il <xref:System.DateTime> valore da convertire e un <xref:System.TimeSpan> offset del valore che rappresenta la data e ora rispetto all'ora UTC. Questo valore di offset deve corrispondere al <xref:System.DateTime.Kind%2A> proprietà del primo parametro del costruttore o un <xref:System.ArgumentException> viene generata un'eccezione. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, il valore del secondo parametro deve essere <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, il valore del secondo parametro deve essere l'offset del fuso orario del sistema locale. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset può essere qualsiasi valore valido. Il codice seguente illustra le chiamate a questo costruttore per convertire <xref:System.DateTime> a <xref:System.DateTimeOffset> valori.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversione implicita del tipo

Il <xref:System.DateTimeOffset> tipo supporta una conversione implicita dei tipi: da un <xref:System.DateTime> valore un <xref:System.DateTimeOffset> valore. Una conversione implicita di tipi è una conversione da un tipo in un altro che non richiede un cast esplicito (in C#) o una conversione esplicita (in Visual Basic) e nella quale non vengono perse informazioni. Rende possibile la scrittura di codice come il seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

L'offset del valore risultante <xref:System.DateTimeOffset> dipende dal valore di <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valore della proprietà. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset è uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se il valore può essere <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset viene impostato come uguale a quello del fuso orario locale.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analisi della rappresentazione di stringa di data e ora

Il <xref:System.DateTimeOffset> tipo supporta quattro metodi che consentono di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore:

* <xref:System.DateTimeOffset.Parse%2A>, che tenta di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore e genera un'eccezione se la conversione non riesce.

* <xref:System.DateTimeOffset.TryParse%2A>, che tenta di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore e restituisce `false` se la conversione non riesce.

* <xref:System.DateTimeOffset.ParseExact%2A>, che tenta di convertire la rappresentazione di stringa di data e ora in un formato specifico in un <xref:System.DateTimeOffset> valore. Il metodo genera un'eccezione se la conversione non riesce.

* <xref:System.DateTimeOffset.TryParseExact%2A>, che tenta di convertire la rappresentazione di stringa di data e ora in un formato specifico in un <xref:System.DateTimeOffset> valore. Il metodo restituisce `false` se la conversione non riesce.

L'esempio seguente illustra le chiamate a ognuno di questi metodi di conversione quattro stringa per creare un'istanza di un <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
