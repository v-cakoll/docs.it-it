---
title: Panoramica sui fusi orari
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], about time zones
- transition time [.NET Framework]
- TimeZoneInfo class, about TimeZoneInfo class
- time zones [.NET Framework], creating
- invalid time [.NET Framework]
- fixed rule [.NET Framework]
- ambiguous time [.NET Framework]
- floating rule [.NET Framework]
- daylight saving time [.NET Framework]
- adjustment rule [.NET Framework]
- time zones [.NET Framework], terminology
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a92a9e92f368b6f2af06c40dc4700e1dec2fcfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="time-zone-overview"></a>Panoramica sui fusi orari

La <xref:System.TimeZoneInfo> classe semplifica la creazione di applicazioni basate sul fuso orario. La <xref:System.TimeZone> classe supporta il funzionamento con il fuso orario locale e il tempo universale coordinato (UTC). La <xref:System.TimeZoneInfo> classe supporta entrambe queste zone nonché qualsiasi fuso orario su quali informazioni predefinita nel Registro di sistema. È inoltre possibile utilizzare <xref:System.TimeZoneInfo> per definire i fusi orari personalizzati che non è disponibili informazioni di sistema.

## <a name="time-zone-essentials"></a>Fuso orario essentials

Un fuso orario è un'area geografica nella quale si usa la stessa ora. In genere, ma non sempre, i fusi orari adiacenti hanno un'ora di differenza. L'ora in un qualsiasi fuso orario del mondo può essere espressa come scostamento rispetto all'ora Coordinated Universal Time (UTC).

Molti fusi orari del mondo supportano l'ora legale. L'ora legale ha lo scopo di massimizzare le ore di luce diurna, con uno spostamento in avanti di un'ora in primavera o a inizio estate e con il ripristino dell'ora normale o solare a fine estate o inizio autunno. Queste modifiche rispetto all'ora solare sono note come regole di rettifica.

La transizione alla e dall'ora legale in un determinato fuso orario può essere definita da una regola di rettifica fissa o mobile. Una regola di rettifica fissa imposta una determinata data in cui si verifica ogni anno la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. Le regole di rettifica mobili, molto più comuni, impostano un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile.

Per i fusi orari che supportano le regole di rettifica, la transizione alla e dall'ora legale crea due tipi di ore anomale: le ore non valide e le ore ambigue. Un'ora non valida è un'ora inesistente creata dalla transizione dall'ora solare all'ora legale. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. Un'ora ambigua è un'ora che può essere mappata su due ore diverse in un singolo fuso orario. Viene creata con la transizione dall'ora legale all'ora solare. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale.

## <a name="time-zone-terminology"></a>Terminologia di fuso orario

Nella tabella seguente sono definiti termini usati comunemente quando si lavora con i fusi orari e si sviluppano applicazioni che rilevano il fuso orario.

| Termine            | Definizione |
| --------------- | ---------- |
| Regola di rettifica | Regola che definisce quando si verifica la transizione dall'ora solare all'ora legale e viceversa. Ogni regola di regolazione ha una data di inizio e fine che definisce la regola quando è attiva (ad esempio, la regola di rettifica è in grado di dal 1 gennaio 1986, il 31 dicembre 2006), delta (la quantità di tempo da cui l'ora solare viene modificato come conseguenza di applicazione di th regola di rettifica e) e le informazioni di data e ora specifiche che devono verificarsi durante il periodo di rettifica le transizioni. Le transizioni possono seguire una regola fissa o una regola mobile. |
| Ora ambigua  | Ora che può essere mappata su due ore diverse in un singolo fuso orario. Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale. |
| Regola fissa      | Regola di rettifica che imposta una determinata data per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. |
| Regola mobile   | Regola di rettifica che imposta un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile. |
| Ora non valida    | Ora inesistente creata dalla transizione dall'ora solare all'ora legale. Si verifica quando l'orologio viene portato avanti, ad esempio durante la transizione dall'ora solare all'ora legale di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. |
| Ora transizione | Informazioni su una modifica di ora specifica, ad esempio la modifica dall'ora legale all'ora solare o viceversa, in un particolare fuso orario. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Fusi orari e la classe TimeZoneInfo

In .NET, un <xref:System.TimeZoneInfo> oggetto rappresenta un fuso orario. Il <xref:System.TimeZoneInfo> classe include un <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> metodo che restituisce una matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Ogni elemento della matrice vengono fornite informazioni sulla transizione da e verso l'ora legale per un determinato periodo di tempo. (Per i fusi orari che non supportano ora legale, il metodo restituisce una matrice vuota). Ogni <xref:System.TimeZoneInfo.AdjustmentRule> oggetto ha un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> e <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> proprietà che definisce la data e ora della transizione da e verso l'ora legale. Il <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> proprietà indica se la transizione è fissa o mobile.

.NET si basa su informazioni sul fuso orario fornite dal sistema operativo Windows e archiviate nel Registro di sistema. A causa del numero di fusi orari della terra, non tutti i fusi orari esistenti sono rappresentati nel Registro di sistema. Inoltre, poiché il Registro di sistema è una struttura dinamica, fusi orari predefiniti può essere aggiunto o rimosso da esso. Infine, il Registro di sistema non contiene necessariamente dati cronologici del fuso orario. Ad esempio, in Windows XP il Registro di sistema contiene dati su un unico set di regolazioni del fuso orario. Windows Vista supporta dati dinamici fuso orario, il che significa che un singolo fuso orario può avere più regole di regolazione che si applicano a intervalli specifici di anni. Tuttavia, la maggior parte dei fusi orari definiti in di Windows Vista del Registro di sistema e il supporto all'ora legale hanno solo uno o due regole di regolazione predefinite.

La dipendenza della <xref:System.TimeZoneInfo> classe sul Registro di sistema indica che un'applicazione non è possibile determinare che un particolare fuso orario è definito nel Registro di sistema. Di conseguenza, se si prevede di creare un'istanza di un fuso orario specifico (diverso dal fuso orario locale o da quello che rappresenta l'ora UTC) è consigliabile usare la gestione delle eccezioni. Inoltre necessario fornire un metodo che consente all'applicazione di continuare se è necessario <xref:System.TimeZoneInfo> dal Registro di sistema non può essere creata un'istanza di oggetto.

Per gestire l'assenza di un fuso orario richiesto, il <xref:System.TimeZoneInfo> classe include un <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo, che è possibile utilizzare per creare fusi orari personalizzati che non si trovano nel Registro di sistema. Per informazioni dettagliate sulla creazione di un fuso orario personalizzato, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md). Inoltre, è possibile utilizzare il <xref:System.TimeZoneInfo.ToSerializedString%2A> per convertire una stringa di un fuso orario appena creato e salvarlo in un archivio dati (ad esempio un database, un file di testo, il Registro di sistema o una risorsa dell'applicazione). È quindi possibile utilizzare il <xref:System.TimeZoneInfo.FromSerializedString%2A> nuovamente al metodo per convertire questa stringa un <xref:System.TimeZoneInfo> oggetto. Per informazioni dettagliate, vedere [procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

Dato che ogni fuso orario è caratterizzato da un offset di base rispetto al fuso orario UTC, nonché da un offset da UTC che riflette eventuali regole di rettifica, un'ora in un fuso orario può essere convertita facilmente nell'ora corrispondente in un altro fuso orario. A tale scopo, il <xref:System.TimeZoneInfo> oggetto include diversi metodi di conversione, tra cui:

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, che converte l'ora UTC per il tempo in un determinato fuso orario.

* <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, che converte l'ora in un determinato fuso orario in formato UTC.

* <xref:System.TimeZoneInfo.ConvertTime%2A>, che converte l'ora in un determinato fuso orario per il tempo in un altro fuso orario designato.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, che utilizza identificatori del fuso orario (anziché <xref:System.TimeZoneInfo> oggetti) come parametri per convertire l'ora in un determinato fuso orario per il tempo in un altro fuso orario designato.

Per informazioni dettagliate sulla conversione degli orari tra fusi orari, vedere [Conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md).

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
