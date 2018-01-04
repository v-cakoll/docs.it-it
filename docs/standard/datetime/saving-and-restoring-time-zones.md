---
title: Salvataggio e ripristino di fusi orari
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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d9451b1b0ff41f32c31ef3574b5684ae5a02e252
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="saving-and-restoring-time-zones"></a>Salvataggio e ripristino di fusi orari

La <xref:System.TimeZoneInfo> classe si basa sul Registro di sistema per recuperare i dati del fuso orario predefiniti. Tuttavia, il Registro di sistema è una struttura dinamica. Inoltre, le informazioni sul fuso orario che contiene il Registro di sistema viene utilizzati principalmente per gestire i tempi e le conversioni per l'anno corrente dal sistema operativo. Questo ha due implicazioni principali per le applicazioni che si basano sui dati del fuso orario accurati:

* Un fuso orario è richiesta da un'applicazione non può essere definito nel Registro di sistema o potrebbe essere stato rinominato o rimosso dal Registro di sistema.

* Un fuso orario definito nel Registro di sistema potrebbero non essere disponibili informazioni sulle regole di rettifica specifica che sono necessarie per le conversioni di fusi orari storici.

La <xref:System.TimeZoneInfo> classe risolve tali limitazioni grazie al supporto della serializzazione (salvataggio) e la deserializzazione (ripristino) di dati del fuso orario.

## <a name="time-zone-serialization-and-deserialization"></a>Fuso orario serializzazione e deserializzazione

Salvataggio e ripristino di un fuso orario da serializzare e deserializzare i dati del fuso orario include solo due chiamate al metodo:

* È possibile serializzare un <xref:System.TimeZoneInfo> oggetto tramite una chiamata di tale oggetto <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo. Il metodo non accetta parametri e restituisce una stringa che contiene informazioni sul fuso orario.

* È possibile deserializzare un <xref:System.TimeZoneInfo> oggetto da una stringa serializzata passando tale stringa per il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> metodo.

## <a name="serialization-and-deserialization-scenarios"></a>Scenari di serializzazione e deserializzazione

La possibilità di salvare (o serializzare) un <xref:System.TimeZoneInfo> oggetto in una stringa e di ripristino (o deserializzare) per un uso successivo aumenta l'utilità e la flessibilità del <xref:System.TimeZoneInfo> classe. In questa sezione vengono esaminate alcune situazioni in cui sono particolarmente utili la serializzazione e deserializzazione.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>La serializzazione e deserializzazione di dati del fuso orario in un'applicazione

Un fuso orario serializzato può essere ripristinato da una stringa quando è necessario. Un'applicazione può essere utile se il fuso orario recuperato dal Registro di sistema è in grado di convertire correttamente una data e ora all'interno di un intervallo di date specifico. Ad esempio, i dati del fuso orario nel Registro di sistema Windows XP supporta una sola regola di regolazione, mentre i fusi orari definiti nel Registro di sistema Windows Vista, in genere forniscono informazioni sulle due regole di regolazione. Ciò significa che le conversioni di ora cronologici potrebbero non essere corrette. Serializzazione e deserializzazione dei dati del fuso orario può gestire questa limitazione.

Nell'esempio seguente, un oggetto personalizzato <xref:System.TimeZoneInfo> è definita classe senza regole di regolazione per rappresentare Fuso ora solare fuso orientale dal 1883 al 1917, prima dell'introduzione dell'ora legale negli Stati Uniti. Il fuso orario personalizzato viene serializzato in una variabile con ambito globale. Il metodo di conversione del fuso orario, `ConvertUtcTime`, viene passato volte Coordinated Universal Time (UTC) da convertire. Se la data e ora si verifica in 1917 o versioni precedenti, il fuso orario solare fuso orientale personalizzato viene ripristinato da una stringa serializzata e sostituisce il fuso orario recuperato dal Registro di sistema.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>Gestione delle eccezioni di fuso orario

Poiché il Registro di sistema è una struttura dinamica, il relativo contenuto è soggetti a modifiche accidentali o intenzionali. Ciò significa che un fuso orario che deve essere definito nel Registro di sistema e che è necessario per un'applicazione per una corretta esecuzione potrebbe essere assente. Senza supporto per la serializzazione di fuso orario e la deserializzazione, è necessario altra scelta che per gestire l'eccezione <xref:System.TimeZoneNotFoundException> terminare l'applicazione. Tuttavia, con la serializzazione di fuso orario e la deserializzazione, è possibile gestire un'eccezione imprevista <xref:System.TimeZoneNotFoundException> ripristinando il fuso orario richiesto da una stringa serializzata e l'applicazione continua a essere eseguita.

Nell'esempio seguente viene creato e serializza un fuso orario centrale Standard personalizzato. Tenta quindi di recuperare il fuso orario centrale Standard dal Registro di sistema. Se l'operazione di recupero genera un'eccezione un <xref:System.TimeZoneNotFoundException> o <xref:System.InvalidTimeZoneException>, il gestore di eccezioni deserializza il fuso orario.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>L'archiviazione di una stringa serializzata e il ripristino in caso di necessità

Negli esempi precedenti sono archiviate informazioni sul fuso orario a una variabile di stringa e ripristinate quando necessario. Tuttavia, la stringa che contiene ora serializzato automaticamente le informazioni sul fuso possono essere archiviati in un supporto di archiviazione, ad esempio un file esterno, un file di risorse incorporato nell'applicazione o il Registro di sistema. Si noti che le informazioni sui fusi orari personalizzati devono essere archiviate separatamente le chiavi di fuso orario del sistema nel Registro di sistema.

Archiviazione di una stringa di fuso orario serializzato in questo modo separa la routine di creazione del fuso orario dall'applicazione stessa. Ad esempio, una routine di creazione del fuso orario può eseguire e creare un file di dati che contiene informazioni cronologiche fuso orario che un'applicazione può utilizzare. Il file di dati può essere quindi essere installato con l'applicazione e può essere aperta e uno o più dei fusi orari può essere deserializzato quando l'applicazione lo richiede.

Per un esempio che utilizza una risorsa incorporata per archiviare i dati serializzati fuso orario, vedere [procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
