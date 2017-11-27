---
title: Creazione di un'istanza di un oggetto DateTimeOffset
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f072aecf45aaaf9bd4aec845a698d6f12916fedb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="instantiating-a-datetimeoffset-object"></a>Creazione di un'istanza di un oggetto DateTimeOffset

Il <xref:System.DateTimeOffset> struttura offre una serie di modi per creare nuovi <xref:System.DateTimeOffset> valori. Molti corrispondono direttamente ai metodi disponibili per la creazione di nuovi <xref:System.DateTime> valori, con miglioramenti che consentono di specificare il valore di data e ora offset dall'ora Coordinated Universal Time (UTC). In particolare, è possibile creare un'istanza di un <xref:System.DateTimeOffset> valore nei modi seguenti:

* Utilizzando una data e ora di valore letterale.

* Chiamando un <xref:System.DateTimeOffset> costruttore.

* Convertendo in modo implicito un valore per <xref:System.DateTimeOffset> valore.

* Analizzando la rappresentazione di stringa di una data e dell'ora.

In questo argomento fornisce maggiori dettagli ed esempi di codice che illustrano questi metodi di creazione di nuovi <xref:System.DateTimeOffset> valori.

## <a name="date-and-time-literals"></a>Valori letterali di data e ora

Per le lingue che lo supportano, uno dei modi più comuni per creare un'istanza di un <xref:System.DateTime> valore consiste nel fornire la data e l'ora come valore letterale hardcoded. Ad esempio, il codice di Visual Basic seguente crea un <xref:System.DateTime> oggetto il cui valore è 1 gennaio 2008, alle 10:00.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>i valori possono inoltre essere inizializzati mediante valori letterali di data e ora, quando si utilizzano i linguaggi che supportano <xref:System.DateTime> valori letterali. Ad esempio, il codice di Visual Basic seguente crea un <xref:System.DateTimeOffset> oggetto.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Come illustrato nell'output di console, il <xref:System.DateTimeOffset> valore creato in questo modo viene assegnato l'offset del fuso orario locale. Ciò significa che un <xref:System.DateTimeOffset> valore assegnato utilizzando un valore letterale carattere non identifica un singolo punto nel tempo se il codice viene eseguito in computer diversi.

## <a name="datetimeoffset-constructors"></a>Costruttori di DateTimeOffset

Il <xref:System.DateTimeOffset> tipo definisce sei costruttori. Quattro corrispondono direttamente a <xref:System.DateTime> costruttori, con un parametro di tipo <xref:System.TimeSpan> che definisce la data e l'offset dell'ora rispetto all'ora UTC. Questi consentono di definire un <xref:System.DateTimeOffset> valore in base al valore del relativo singoli componenti di data e ora. Ad esempio, il codice seguente utilizza questi quattro costruttori per creare un'istanza <xref:System.DateTimeOffset> oggetti con valori identici di 1/7/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Si noti che, quando il valore di <xref:System.DateTimeOffset> oggetto implementato con un <xref:System.Globalization.PersianCalendar> oggetto come uno degli argomenti al costruttore è visualizzata nella console, viene espresso come data del calendario gregoriano anziché il calendario persiano. Per restituire una data utilizzando il calendario persiano, vedere l'esempio nel <xref:System.Globalization.PersianCalendar> argomento.

Gli altri due costruttori creano un <xref:System.DateTimeOffset> dell'oggetto da un <xref:System.DateTime> valore. Il primo dei quali presenta un singolo parametro, il <xref:System.DateTime> valore da convertire in un <xref:System.DateTimeOffset> valore. L'offset del valore risultante <xref:System.DateTimeOffset> dipende dal valore di <xref:System.DateTime.Kind%2A> proprietà del solo parametro del costruttore. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset è uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. In caso contrario, l'offset viene impostato su un valore uguale a quello del fuso orario locale. Nell'esempio seguente viene illustrato l'utilizzo di questo costruttore per creare un'istanza <xref:System.DateTimeOffset> gli oggetti che rappresentano l'ora UTC e il fuso orario locale:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Chiamare l'overload di <xref:System.DateTimeOffset> costruttore con un singolo <xref:System.DateTime> parametro equivale all'esecuzione di una conversione implicita di un <xref:System.DateTime> valore un <xref:System.DateTimeOffset> valore.

Il secondo costruttore crea un <xref:System.DateTimeOffset> dell'oggetto da un <xref:System.DateTime> valore presenta due parametri: il <xref:System.DateTime> valore da convertire e un <xref:System.TimeSpan> offset del valore che rappresenta la data e l'ora dall'ora UTC. Questo valore di offset deve corrispondere al <xref:System.DateTime.Kind%2A> proprietà del primo parametro del costruttore o un <xref:System.ArgumentException> viene generata un'eccezione. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, il valore del secondo parametro deve essere <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, il valore del secondo parametro deve essere l'offset del fuso orario del sistema locale. Se il <xref:System.DateTime.Kind%2A> proprietà del primo parametro è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset può essere qualsiasi valore valido. Il codice riportato di seguito sono illustrate le chiamate a questo costruttore per convertire <xref:System.DateTime> a <xref:System.DateTimeOffset> valori.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Conversione implicita del tipo

Il <xref:System.DateTimeOffset> tipo supporta una conversione implicita dei tipi: da un <xref:System.DateTime> valore un <xref:System.DateTimeOffset> valore. Una conversione implicita di tipi è una conversione da un tipo in un altro che non richiede un cast esplicito (in C#) o una conversione esplicita (in Visual Basic) e nella quale non vengono perse informazioni. Rende possibile la scrittura di codice come il seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

L'offset del valore risultante <xref:System.DateTimeOffset> dipende dal valore di <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valore della proprietà. Se il valore è <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, l'offset è uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Se il valore è <xref:System.DateTimeKind.Local?displayProperty=nameWithType> o <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, l'offset è uguale a quella del fuso orario locale.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analisi della rappresentazione di stringa di una data e ora

Il <xref:System.DateTimeOffset> tipo supporta quattro metodi che consentono di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore:

* <xref:System.DateTimeOffset.Parse%2A>, che tenta di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore e genera un'eccezione se la conversione non riesce.

* <xref:System.DateTimeOffset.TryParse%2A>, che tenta di convertire la rappresentazione di stringa di una data e ora in un <xref:System.DateTimeOffset> valore e restituisce `false` se la conversione non riesce.

* <xref:System.DateTimeOffset.ParseExact%2A>, che tenta di convertire la rappresentazione di stringa di data e ora in un formato specificato in un <xref:System.DateTimeOffset> valore. Il metodo genera un'eccezione se la conversione non riesce.

* <xref:System.DateTimeOffset.TryParseExact%2A>, che tenta di convertire la rappresentazione di stringa di data e ora in un formato specificato in un <xref:System.DateTimeOffset> valore. Il metodo restituisce `false` se la conversione non riesce.

L'esempio seguente illustra le chiamate a ognuno di questi metodi di conversione della stringa di quattro per creare un'istanza di un <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
