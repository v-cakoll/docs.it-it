---
title: Panoramica sui fusi orari
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0eb24c7c4f2c60a9c16d903ab1e845b058e280f7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615365"
---
# <a name="time-zone-overview"></a>Panoramica sui fusi orari

Il <xref:System.TimeZoneInfo> classe semplifica la creazione di applicazioni che dipendono dal fuso orario. Il <xref:System.TimeZone> classe supporta l'uso con il fuso orario locale e Coordinated Universal Time (UTC). Il <xref:System.TimeZoneInfo> classe supporta entrambe queste zone predefinita nonché qualsiasi fuso orario su quali informazioni nel Registro di sistema. È anche possibile usare <xref:System.TimeZoneInfo> per definire fusi orari personalizzati che non è disponibili informazioni di sistema.

## <a name="time-zone-essentials"></a>Informazioni essenziali sui fusi

Un fuso orario è un'area geografica nella quale si usa la stessa ora. In genere, ma non sempre, i fusi orari adiacenti hanno un'ora di differenza. L'ora in un qualsiasi fuso orario del mondo può essere espressa come scostamento rispetto all'ora Coordinated Universal Time (UTC).

Molti fusi orari del mondo supportano l'ora legale. L'ora legale ha lo scopo di massimizzare le ore di luce diurna, con uno spostamento in avanti di un'ora in primavera o a inizio estate e con il ripristino dell'ora normale o solare a fine estate o inizio autunno. Queste modifiche rispetto all'ora solare sono note come regole di rettifica.

La transizione alla e dall'ora legale in un determinato fuso orario può essere definita da una regola di rettifica fissa o mobile. Una regola di rettifica fissa imposta una determinata data in cui si verifica ogni anno la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. Le regole di rettifica mobili, molto più comuni, impostano un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile.

Per i fusi orari che supportano le regole di rettifica, la transizione alla e dall'ora legale crea due tipi di ore anomale: le ore non valide e le ore ambigue. Un'ora non valida è un'ora inesistente creata dalla transizione dall'ora solare all'ora legale. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. Un'ora ambigua è un'ora che può essere mappata su due ore diverse in un singolo fuso orario. Viene creata con la transizione dall'ora legale all'ora solare. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale.

## <a name="time-zone-terminology"></a>Terminologia di fuso orario

Nella tabella seguente sono definiti termini usati comunemente quando si lavora con i fusi orari e si sviluppano applicazioni che rilevano il fuso orario.

| Termine            | Definizione |
| --------------- | ---------- |
| Regola di rettifica | Regola che definisce quando si verifica la transizione dall'ora solare all'ora legale e viceversa. Ogni regola di rettifica ha una data di inizio e fine che definisce quando la regola è posto (ad esempio, la regola di rettifica è in grado di dal 1 gennaio 1986 al 31 dicembre 2006), delta (la quantità di tempo mediante il quale viene modificato l'ora solare come conseguenza l'applicazione dell'ennesimo regola di rettifica e) e le informazioni di data e ora specifiche che devono verificarsi durante il periodo di regolazione le transizioni. Le transizioni possono seguire una regola fissa o una regola mobile. |
| Ora ambigua  | Ora che può essere mappata su due ore diverse in un singolo fuso orario. Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale. |
| Regola fissa      | Regola di rettifica che imposta una determinata data per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. |
| Regola mobile   | Regola di rettifica che imposta un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile. |
| Ora non valida    | Ora inesistente creata dalla transizione dall'ora solare all'ora legale. Si verifica quando l'orologio viene portato avanti, ad esempio durante la transizione dall'ora solare all'ora legale di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. |
| Ora transizione | Informazioni su una modifica di ora specifica, ad esempio la modifica dall'ora legale all'ora solare o viceversa, in un particolare fuso orario. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Fusi orari e classe TimeZoneInfo

In .NET un <xref:System.TimeZoneInfo> oggetto rappresenta un fuso orario. Il <xref:System.TimeZoneInfo> classe include una <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> metodo che restituisce una matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Ogni elemento della matrice vengono fornite informazioni sulla transizione da e verso l'ora legale per un periodo di tempo specifico. (Per i fusi orari che non supportano l'ora legale, il metodo restituisce una matrice vuota). Ciascuna <xref:System.TimeZoneInfo.AdjustmentRule> oggetto ha un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> e un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> proprietà che definisce la data e ora della transizione alla e dall'ora legale. Il <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> proprietà indica se tale transizione è fissa o mobile.

.NET si basa su informazioni sul fuso orario fornito dal sistema operativo Windows e archiviate nel Registro di sistema. A causa del numero dei fusi orari della terra, non tutti i fusi orari esistenti vengono rappresentati nel Registro di sistema. Inoltre, poiché il Registro di sistema è una struttura dinamica, fusi orari predefiniti può essere aggiunto a o rimossi da essa. Infine, il Registro di sistema non contiene necessariamente dati cronologici del fuso orario. In Windows XP, ad esempio, il Registro di sistema contiene dati relativi a un solo set di regolazioni del fuso orario. Windows Vista supporta dati dinamici al fuso orario, il che significa che un singolo fuso orario può avere più regole di regolazione che si applicano a intervalli specifici di anni. Tuttavia, la maggior parte dei fusi orari definiti in di Windows Vista del Registro di sistema e supporto per l'ora legale avere solo uno o due regole di regolazione predefiniti.

La dipendenza del <xref:System.TimeZoneInfo> classe nel Registro di sistema significa che un'applicazione compatibile con fuso orario può essere certi che un determinato fuso orario viene definito nel Registro di sistema. Di conseguenza, se si prevede di creare un'istanza di un fuso orario specifico (diverso dal fuso orario locale o da quello che rappresenta l'ora UTC) è consigliabile usare la gestione delle eccezioni. Inoltre necessario fornire un metodo che consente all'applicazione di continuare se necessaria <xref:System.TimeZoneInfo> dal Registro di sistema non è possibile creare un'istanza di oggetto.

Per gestire l'assenza di un fuso orario richiesto, il <xref:System.TimeZoneInfo> classe include una <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo, che è possibile usare per creare fusi orari personalizzati che non si trovano nel Registro di sistema. Per informazioni dettagliate sulla creazione di un fuso orario personalizzato, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md). Inoltre, è possibile usare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per convertire un fuso orario appena creato in una stringa e salvarlo in un archivio dati (ad esempio, un database, un file di testo, il Registro di sistema o una risorsa applicazione). È quindi possibile usare la <xref:System.TimeZoneInfo.FromSerializedString%2A> eseguire il metodo per convertire questa stringa in un <xref:System.TimeZoneInfo> oggetto. Per informazioni dettagliate, vedere [procedura: salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

Dato che ogni fuso orario è caratterizzato da un offset di base rispetto al fuso orario UTC, nonché da un offset da UTC che riflette eventuali regole di rettifica, un'ora in un fuso orario può essere convertita facilmente nell'ora corrispondente in un altro fuso orario. A tale scopo, il <xref:System.TimeZoneInfo> oggetto include diversi metodi di conversione, tra cui:

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, che converte l'ora UTC nell'ora di un determinato fuso orario.

* <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, che converte l'ora in un determinato fuso orario in ora UTC.

* <xref:System.TimeZoneInfo.ConvertTime%2A>, che converte l'ora in un determinato fuso orario all'ora in un altro fuso orario designato.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, che utilizza gli identificatori di fuso orario (anziché <xref:System.TimeZoneInfo> oggetti) come parametri per convertire l'ora in un determinato fuso orario all'ora in un altro fuso orario designato.

Per informazioni dettagliate sulla conversione degli orari tra fusi orari, vedere [Conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md).

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
