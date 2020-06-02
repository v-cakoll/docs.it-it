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
ms.openlocfilehash: 8da26988d2e141ac704f0d3756cd8a50602cb3fd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281050"
---
# <a name="saving-and-restoring-time-zones"></a>Salvataggio e ripristino dei fusi orari

La <xref:System.TimeZoneInfo> classe si basa sul Registro di sistema per recuperare i dati del fuso orario predefiniti. Tuttavia, il registro di sistema è una struttura dinamica. Inoltre, le informazioni sul fuso orario contenute nel registro di sistema vengono utilizzate principalmente dal sistema operativo per gestire le regolazioni e le conversioni di tempo per l'anno corrente. Questo ha due implicazioni principali per le applicazioni che si basano sui dati accurati del fuso orario:

- Un fuso orario richiesto da un'applicazione potrebbe non essere definito nel registro di sistema oppure è possibile che sia stato rinominato o rimosso dal registro di sistema.

- Un fuso orario definito nel registro di sistema potrebbe non essere in grado di ottenere informazioni sulle specifiche regole di rettifica necessarie per le conversioni cronologiche del fuso orario.

La <xref:System.TimeZoneInfo> classe risolve queste limitazioni attraverso il supporto per la serializzazione (salvataggio) e la deserializzazione (ripristino) dei dati del fuso orario.

## <a name="time-zone-serialization-and-deserialization"></a>Serializzazione e deserializzazione del fuso orario

Il salvataggio e il ripristino di un fuso orario tramite la serializzazione e la deserializzazione dei dati del fuso orario implicano solo due chiamate al metodo:

- È possibile serializzare un <xref:System.TimeZoneInfo> oggetto chiamando il metodo di tale oggetto <xref:System.TimeZoneInfo.ToSerializedString%2A> . Il metodo non accetta parametri e restituisce una stringa che contiene le informazioni sul fuso orario.

- È possibile deserializzare un <xref:System.TimeZoneInfo> oggetto da una stringa serializzata passando la stringa al `static` `Shared` metodo (in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> .

## <a name="serialization-and-deserialization-scenarios"></a>Scenari di serializzazione e deserializzazione

La possibilità di salvare (o serializzare) un <xref:System.TimeZoneInfo> oggetto in una stringa e di ripristinarla (o deserializzarla) per un uso successivo aumenta sia l'utilità che la flessibilità della <xref:System.TimeZoneInfo> classe. In questa sezione vengono esaminate alcune delle situazioni in cui la serializzazione e la deserializzazione sono molto utili.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>Serializzazione e deserializzazione dei dati del fuso orario in un'applicazione

Un fuso orario serializzato può essere ripristinato da una stringa quando è necessario. Un'applicazione può eseguire questa operazione se il fuso orario recuperato dal registro di sistema non è in grado di convertire correttamente una data e un'ora in un intervallo di date specifico. Ad esempio, i dati del fuso orario nel registro di sistema di Windows XP supportano una singola regola di regolazione, mentre i fusi orari definiti nel registro di sistema di Windows Vista forniscono in genere informazioni su due regole di rettifica. Ciò significa che le conversioni cronologiche del tempo potrebbero non essere accurate. La serializzazione e la deserializzazione dei dati del fuso orario possono gestire questa limitazione.

Nell'esempio seguente, una classe <xref:System.TimeZoneInfo> personalizzata senza regole di modifica viene definita per rappresentare il fuso orario standard degli Stati Uniti orientali dal 1883 al 1917, prima dell'introduzione dell'ora legale negli Stati Uniti. Il fuso orario personalizzato viene serializzato in una variabile con ambito globale. Il metodo di conversione del fuso orario, `ConvertUtcTime` , viene passato per le ore UTC (Coordinated Universal Time) per la conversione. Se la data e l'ora si verificano in 1917 o versioni precedenti, il fuso orario standard orientale personalizzato viene ripristinato da una stringa serializzata e sostituisce il fuso orario recuperato dal registro di sistema.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Gestione delle eccezioni del fuso orario

Poiché il registro di sistema è una struttura dinamica, il relativo contenuto è soggetto a modifiche accidentali o intenzionali. Ciò significa che un fuso orario che deve essere definito nel registro di sistema e che è necessario per l'esecuzione corretta di un'applicazione potrebbe essere assente. Senza il supporto per la serializzazione e la deserializzazione del fuso orario, è possibile scegliere di gestire il risultante <xref:System.TimeZoneNotFoundException> terminando l'applicazione. Tuttavia, usando la serializzazione e la deserializzazione del fuso orario, è possibile gestire un valore imprevisto <xref:System.TimeZoneNotFoundException> ripristinando il fuso orario necessario da una stringa serializzata e l'applicazione continuerà a essere eseguita.

Nell'esempio seguente viene creato e serializzato un fuso orario standard centrale personalizzato. Tenta quindi di recuperare il fuso orario standard centrale dal registro di sistema. Se l'operazione di recupero genera un' <xref:System.TimeZoneNotFoundException> <xref:System.InvalidTimeZoneException> eccezione o, il gestore di eccezioni deserializza il fuso orario.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Archiviazione di una stringa serializzata e ripristino quando necessario

Negli esempi precedenti le informazioni sul fuso orario sono state archiviate in una variabile di stringa e ripristinate quando necessario. Tuttavia, la stringa che contiene informazioni serializzate sul fuso orario può essere archiviata in un supporto di archiviazione, ad esempio un file esterno, un file di risorse incorporato nell'applicazione o il registro di sistema. Si noti che le informazioni sui fusi orari personalizzati devono essere archiviate a parte le chiavi del fuso orario del sistema nel registro di sistema.

L'archiviazione di una stringa di fuso orario serializzata in questo modo separa anche la routine di creazione del fuso orario dall'applicazione stessa. Ad esempio, una routine di creazione del fuso orario può eseguire e creare un file di dati che contiene informazioni cronologiche sul fuso orario che possono essere utilizzate da un'applicazione. Il file di dati può essere quindi installato con l'applicazione e può essere aperto e uno o più dei relativi fusi orari possono essere deserializzati quando sono necessari per l'applicazione.

Per un esempio in cui viene usata una risorsa incorporata per archiviare i dati dei fusi orari serializzati, vedere [procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
