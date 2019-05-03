---
title: Date, ore e fusi orari
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5355666b95d75fc18d0188c978c186690ee9ccca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61819704"
---
# <a name="dates-times-and-time-zones"></a>Date, ore e fusi orari

Oltre alla struttura di base <xref:System.DateTime>, .NET fornisce le classi seguenti che supportano l'uso dei fusi orari:

* <xref:System.TimeZone>

  Usare questa classe con il fuso orario locale del sistema e il fuso UTC (Coordinated Universal Time). La funzionalità della classe <xref:System.TimeZone> è ampiamente sostituita dalla classe <xref:System.TimeZoneInfo>.

* <xref:System.TimeZoneInfo>

  Utilizzare questa classe per utilizzare qualsiasi fuso orario predefinito in un sistema, per creare nuovi fusi orari e per convertire facilmente date e ore da un fuso orario a un altro. Per i nuovi progetti di sviluppo usare la classe <xref:System.TimeZoneInfo> anziché la classe <xref:System.TimeZone>.

* <xref:System.DateTimeOffset>

  Usare questa struttura con le date e le ore il cui offset (o differenza) rispetto all'ora UTC è noto. La struttura <xref:System.DateTimeOffset> combina un valore di data e ora con l'offset di quell'ora rispetto all'ora UTC. Per via della relazione con l'ora UTC, un singolo valore di data e ora identifica un momento specifico senza ambiguità. Un valore <xref:System.DateTimeOffset> risulta pertanto più portabile da un computer a un altro rispetto a un valore <xref:System.DateTime>.

Questa sezione della documentazione include le informazioni necessarie per usare i fusi orari e per creare applicazioni in grado di riconoscere i fusi orari e convertire date e ore da un fuso orario a un altro.

## <a name="in-this-section"></a>Contenuto della sezione

[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md) Illustra concetti, terminologia e problemi relativi alla creazione di applicazioni che dipendono dal fuso orario.

[Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Illustra quando usare i tipi <xref:System.DateTime>, <xref:System.DateTimeOffset> e <xref:System.TimeZoneInfo> con i dati relativi a data e ora.

[Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Descrive come enumerare i fusi orari disponibili in un sistema locale.

[Procedura: Enumerare i fusi orari presenti in un computer](../../../docs/standard/datetime/enumerate-time-zones.md) vengono forniti esempi che enumerano i fusi orari definiti nel Registro di sistema del computer e che consentono agli utenti di selezionare un fuso orario predefinito da un elenco.

[Procedura: Accedere ora UTC e l'ora locale zona agli oggetti predefiniti](../../../docs/standard/datetime/access-utc-and-local.md) viene descritto come accedere all'ora UTC e il fuso orario locale.

[Procedura: Creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md) descrive come creare un'istanza di un <xref:System.TimeZoneInfo> oggetto dal Registro di sistema locale.

[Creazione di un'istanza di un oggetto DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Illustra i modi per creare un'istanza di un oggetto <xref:System.DateTimeOffset> e i modi per convertire un valore <xref:System.DateTime> in un valore <xref:System.DateTimeOffset>.

[Procedura: Creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) viene descritto come creare un fuso orario personalizzato che non supporta la transizione alla e dall'ora legale.

[Procedura: Creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) viene descritto come creare un fuso orario personalizzato che supporta uno o più transizioni da e verso l'ora legale.

[Salvataggio e ripristino dei fusi orari](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Descrive il supporto <xref:System.TimeZoneInfo> per la serializzazione e deserializzazione dei dati del fuso orario e illustra alcuni degli scenari in cui è possibile usare tali funzionalità.

[Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) viene descritto come creare un fuso orario personalizzato e salvare le informazioni in un file di risorse.

[Procedura: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) viene descritto come creare un'istanza di fusi orari personalizzati che sono stati salvati in un file di risorsa incorporata.

[Esecuzione di operazioni aritmetiche con date e ore](../../../docs/standard/datetime/performing-arithmetic-operations.md) Descrive i problemi relativi ad aggiunta, sottrazione e confronto dei valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.

[Procedura: Usare fusi orari nella data e ora aritmetico](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) illustra come eseguire la data e ora aritmetico che riflettano le regole di regolazione del fuso orario.

[Conversione tra DateTime e DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Descrive come eseguire la conversione tra i valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.

[Conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md) Descrive come eseguire la conversione di ore tra un fuso orario e un altro.

[Procedura: Risolvere orari ambigui](../../../docs/standard/datetime/resolve-ambiguous-times.md) descrive come risolvere un orario ambiguo eseguendone il mapping all'ora solare del fuso orario.

[Procedura: Consentire agli utenti di risolvere orari ambigui](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) viene descritto come consentire agli utenti di determinare il mapping tra un'ora locale ambigua e l'ora UTC.

## <a name="reference"></a>Riferimenti

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
