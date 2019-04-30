---
title: Salvataggio e ripristino dei fusi orari
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d783f9e0d098e472dcf67aea394804d6eef2662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026523"
---
# <a name="saving-and-restoring-time-zones"></a>Salvataggio e ripristino dei fusi orari

Il <xref:System.TimeZoneInfo> classe si basa sul Registro di sistema per recuperare i dati di fuso orario predefinito. Tuttavia, il Registro di sistema è una struttura dinamica. Inoltre, le informazioni sul fuso orario che contiene il Registro di sistema viene utilizzate dal sistema operativo principalmente per gestire le conversioni e regolazioni dell'ora per l'anno corrente. Ciò comporta due implicazioni principali per le applicazioni basate sui dati del fuso orario accurati:

* Un fuso orario che è richiesto da un'applicazione non può essere definito nel Registro di sistema o potrebbe essere stato rinominato o rimosso dal Registro di sistema.

* Un fuso orario definito nel Registro di sistema potrebbero non essere disponibili informazioni sulle regole di rettifica specifica che sono necessarie per conversioni di fusi orari storici.

Il <xref:System.TimeZoneInfo> classe indirizza queste limitazioni grazie al supporto della serializzazione (salvataggio) e la deserializzazione (ripristino) di dati del fuso orario.

## <a name="time-zone-serialization-and-deserialization"></a>Fuso orario serializzazione e deserializzazione

Salvataggio e ripristino di un fuso orario da serializzare e deserializzare i dati del fuso orario prevede solo due chiamate al metodo:

* È possibile serializzare una <xref:System.TimeZoneInfo> chiamando tale oggetto <xref:System.TimeZoneInfo.ToSerializedString%2A> (metodo). Il metodo non accetta parametri e restituisce una stringa che contiene informazioni sul fuso orario.

* È possibile deserializzare un <xref:System.TimeZoneInfo> oggetto da una stringa serializzata passando tale stringa per il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> (metodo).

## <a name="serialization-and-deserialization-scenarios"></a>Scenari di serializzazione e deserializzazione

La possibilità di salvare (o serializzare) una <xref:System.TimeZoneInfo> oggetti in una stringa e di ripristino (o deserializzare) per un uso successivo aumentano l'utilità e la flessibilità del <xref:System.TimeZoneInfo> classe. In questa sezione vengono esaminate alcune delle situazioni in cui la serializzazione e deserializzazione sono particolarmente utili.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>La serializzazione e deserializzazione di dati del fuso orario di un'applicazione

Quando è necessario, un fuso orario serializzato può essere ripristinato da una stringa. Un'applicazione può eseguire questa operazione se il fuso orario recuperato dal Registro di sistema è in grado di convertire correttamente una data e ora in un intervallo di date specifico. Ad esempio, dati del fuso orario nel Registro di sistema Windows XP supportano una regola di rettifica singolo, mentre i fusi orari definiti nel Registro di sistema Windows Vista in genere forniscono informazioni sulle due regole di regolazione. Ciò significa che le conversioni di tempo cronologici della durata potrebbero non essere corrette. Serializzazione e deserializzazione dei dati del fuso orario può gestire questa limitazione.

Nell'esempio seguente, una classe personalizzata <xref:System.TimeZoneInfo> classe che non dispone di alcuna regola di rettifica viene definita per rappresentare gli Stati Uniti Ora solare fuso dal 1883 al 1917, prima dell'introduzione dell'ora legale negli Stati Uniti. Il fuso orario personalizzato viene serializzato in una variabile con ambito globale. Il metodo di conversione del fuso orario, `ConvertUtcTime`, viene passato volte Coordinated Universal Time (UTC) da convertire. Se la data e ora si verifica in 1917 o versioni precedenti, il fuso orario solare personalizzato è stato ripristinato da una stringa serializzata e sostituisce il fuso orario recuperato dal Registro di sistema.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Gestione delle eccezioni di fuso orario

Poiché il Registro di sistema è una struttura dinamica, il relativo contenuto è soggetti a modifiche accidentali o intenzionali. Ciò significa che un fuso orario che deve essere definito nel Registro di sistema e che è necessario eseguire correttamente un'applicazione può essere assente. Senza il supporto per la serializzazione di fuso orario e la deserializzazione, le scelte sono poche ma per gestire l'eccezione <xref:System.TimeZoneNotFoundException> terminando l'applicazione. Tuttavia, con la serializzazione di fuso orario e la deserializzazione, è possibile gestire un'eccezione imprevista <xref:System.TimeZoneNotFoundException> ripristinando il fuso orario richiesto da una stringa serializzata e l'applicazione continuerà a essere eseguito.

Nell'esempio seguente crea e serializza un fuso orario Standard centrale personalizzato. Quindi tenta di recuperare il fuso orario Standard centrale dal Registro di sistema. Se l'operazione di recupero genera un'eccezione una <xref:System.TimeZoneNotFoundException> o un <xref:System.InvalidTimeZoneException>, il gestore di eccezioni deserializza il fuso orario.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>L'archiviazione di una stringa serializzata e il ripristino in caso di necessità

Negli esempi precedenti sono archiviate informazioni sul fuso orario a una variabile di stringa e ripristinati in caso di necessità. Tuttavia, la stringa che contiene ora serializzata stesso le informazioni sulla zona possono essere archiviati in un supporto di archiviazione, ad esempio un file esterno, un file di risorse incorporato nell'applicazione o il Registro di sistema. Si noti che le informazioni sui fusi orari personalizzati devono essere archiviate oltre alle chiavi di fuso orario del sistema nel Registro di sistema.

Archiviazione di una stringa serializzata fuso orario in questo modo anche separa le routine di creazione del fuso orario dall'applicazione stessa. Ad esempio, una routine di creazione del fuso orario può eseguire e creare un file di dati che contiene informazioni cronologiche fuso orario che un'applicazione può usare. Il file di dati può essere quindi essere installato con l'applicazione e può essere aperto e uno o più dei fusi orari può essere deserializzato quando l'applicazione lo richiede.

Per un esempio che usa una risorsa incorporata per archiviare dati serializzati del fuso orario, vedere [come: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [come: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
