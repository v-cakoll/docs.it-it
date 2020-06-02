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
ms.openlocfilehash: 86602cd6e662b1b1057832247babc558ef67b79f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276933"
---
# <a name="dates-times-and-time-zones"></a>Date, ore e fusi orari

Oltre alla struttura di base <xref:System.DateTime>, .NET fornisce le classi seguenti che supportano l'uso dei fusi orari:

* <xref:System.TimeZone>

  Usare questa classe con il fuso orario locale del sistema e il fuso UTC (Coordinated Universal Time). La funzionalità della <xref:System.TimeZone> classe è ampiamente sostituita dalla <xref:System.TimeZoneInfo> classe.

* <xref:System.TimeZoneInfo>

  Utilizzare questa classe per utilizzare qualsiasi fuso orario predefinito in un sistema, per creare nuovi fusi orari e per convertire facilmente date e ore da un fuso orario a un altro. Per i nuovi progetti di sviluppo usare la classe <xref:System.TimeZoneInfo> anziché la classe <xref:System.TimeZone>.

* <xref:System.DateTimeOffset>

  Usare questa struttura con le date e le ore il cui offset (o differenza) rispetto all'ora UTC è noto. La struttura <xref:System.DateTimeOffset> combina un valore di data e ora con l'offset di quell'ora rispetto all'ora UTC. Per via della relazione con l'ora UTC, un singolo valore di data e ora identifica un momento specifico senza ambiguità. Un valore <xref:System.DateTimeOffset> risulta pertanto più portabile da un computer a un altro rispetto a un valore <xref:System.DateTime>.

Questa sezione della documentazione include le informazioni necessarie per usare i fusi orari e per creare applicazioni in grado di riconoscere i fusi orari e convertire date e ore da un fuso orario a un altro.

## <a name="in-this-section"></a>Contenuto della sezione

[Panoramica sul fuso orario](time-zone-overview.md): illustra concetti, terminologia e problemi relativi alla creazione di applicazioni che dipendono dal fuso orario.

[Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](choosing-between-datetime.md) Viene illustrato quando utilizzare i <xref:System.DateTime> tipi, e quando si utilizzano i <xref:System.DateTimeOffset> <xref:System.TimeZoneInfo> dati di data e ora.

[Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md): descrive come enumerare i fusi orari che si trovano in un sistema locale.

[Procedura: Enumerare i fusi orari presenti in un computer](enumerate-time-zones.md): include esempi che enumerano i fusi orari definiti nel Registro di sistema di un computer e che consentono agli utenti di selezionare un fuso orario predefinito da un elenco.

[Procedura: Accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md): descrive come accedere all'ora UTC e al fuso orario locale.

[Procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md) Descrive come creare un'istanza di un oggetto <xref:System.TimeZoneInfo> dal Registro di sistema locale.

[Creazione di un'istanza di un oggetto DateTimeOffset](instantiating-a-datetimeoffset-object.md) Illustra i modi per creare un'istanza di un oggetto <xref:System.DateTimeOffset> e i modi per convertire un valore <xref:System.DateTime> in un valore <xref:System.DateTimeOffset>.

[Procedura: Creare fusi orari senza regole di regolazione](create-time-zones-without-adjustment-rules.md): descrive come creare un fuso orario personalizzato che non supporta la transizione da e verso l'ora legale.

[Procedura: Creare fusi orari con regole di regolazione](create-time-zones-with-adjustment-rules.md): descrive come creare un fuso orario personalizzato che supporta una o più transizioni da e verso l'ora legale.

[Salvataggio e ripristino dei fusi orari](saving-and-restoring-time-zones.md) Descrive il supporto <xref:System.TimeZoneInfo> per la serializzazione e deserializzazione dei dati del fuso orario e illustra alcuni degli scenari in cui è possibile usare tali funzionalità.

[Procedura: Salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md): descrive come creare un fuso orario personalizzato e salvare le informazioni in un file di risorse.

[Procedura: Ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md): descrive come creare un'istanza di fusi orari personalizzati che sono stati salvati in un file di risorsa incorporata.

[Esecuzione di operazioni aritmetiche con date e ore](performing-arithmetic-operations.md) Descrive i problemi relativi ad aggiunta, sottrazione e confronto dei valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.

[Procedura: Usare fusi orari nell'aritmetica di data e ora](use-time-zones-in-arithmetic.md): illustra come eseguire operazioni aritmetiche di data e ora che riflettano le regole di regolazione di un fuso orario.

[Conversione tra DateTime e DateTimeOffset](converting-between-datetime-and-offset.md) Descrive come eseguire la conversione tra i valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.

[Conversione degli orari tra fusi orari](converting-between-time-zones.md): descrive come eseguire la conversione di ore tra un fuso orario e un altro.

[Procedura: Risolvere orari ambigui](resolve-ambiguous-times.md): descrive come risolvere un orario ambiguo eseguendone il mapping all'ora solare del fuso orario.

[Procedura: Consentire agli utenti di risolvere orari ambigui](let-users-resolve-ambiguous-times.md): descrive come consentire agli utenti di determinare il mapping tra un'ora locale ambigua e l'ora UTC.

## <a name="reference"></a>Informazioni di riferimento

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
