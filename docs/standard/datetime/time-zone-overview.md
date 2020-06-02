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
ms.openlocfilehash: 9cb50357931cb22fd2862ba7558154a4782e4557
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281037"
---
# <a name="time-zone-overview"></a>Panoramica sui fusi orari

La <xref:System.TimeZoneInfo> classe semplifica la creazione di applicazioni in grado di riconoscere il fuso orario. La <xref:System.TimeZone> classe supporta l'utilizzo del fuso orario locale e dell'ora UTC (Coordinated Universal Time). La <xref:System.TimeZoneInfo> classe supporta entrambe le zone, nonché qualsiasi fuso orario per il quale le informazioni sono predefinite nel registro di sistema. È inoltre possibile utilizzare <xref:System.TimeZoneInfo> per definire fusi orari personalizzati per cui il sistema non dispone di informazioni.

## <a name="time-zone-essentials"></a>Elementi di base del fuso orario

Un fuso orario è un'area geografica nella quale si usa la stessa ora. In genere, ma non sempre, i fusi orari adiacenti hanno un'ora di differenza. L'ora in un qualsiasi fuso orario del mondo può essere espressa come scostamento rispetto all'ora Coordinated Universal Time (UTC).

Molti fusi orari del mondo supportano l'ora legale. L'ora legale ha lo scopo di massimizzare le ore di luce diurna, con uno spostamento in avanti di un'ora in primavera o a inizio estate e con il ripristino dell'ora normale o solare a fine estate o inizio autunno. Queste modifiche rispetto all'ora solare sono note come regole di rettifica.

La transizione alla e dall'ora legale in un determinato fuso orario può essere definita da una regola di rettifica fissa o mobile. Una regola di rettifica fissa imposta una determinata data in cui si verifica ogni anno la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. Le regole di rettifica mobili, molto più comuni, impostano un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile.

Per i fusi orari che supportano le regole di rettifica, la transizione alla e dall'ora legale crea due tipi di ore anomale: le ore non valide e le ore ambigue. Un'ora non valida è un'ora inesistente creata dalla transizione dall'ora solare all'ora legale. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. Un'ora ambigua è un'ora che può essere mappata su due ore diverse in un singolo fuso orario. Viene creata con la transizione dall'ora legale all'ora solare. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale.

## <a name="time-zone-terminology"></a>Terminologia del fuso orario

Nella tabella seguente sono definiti termini usati comunemente quando si lavora con i fusi orari e si sviluppano applicazioni che rilevano il fuso orario.

| Termine            | Definizione |
| --------------- | ---------- |
| Regola di rettifica | Regola che definisce quando si verifica la transizione dall'ora solare all'ora legale e viceversa. Ogni regola di regolazione presenta una data di inizio e di fine che definisce quando la regola è attiva, ad esempio la regola di rettifica è stata eseguita dal 1 ° gennaio 1986 al 31 dicembre 2006), un Delta (il periodo di tempo in cui l'ora solare cambia in seguito all'applicazione della regola di rettifica) e informazioni sulla data e l'ora specifiche in cui devono verificarsi le transizioni durante il periodo di regolazione. Le transizioni possono seguire una regola fissa o una regola mobile. |
| Ora ambigua  | Ora che può essere mappata su due ore diverse in un singolo fuso orario. Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 1.00, ogni intervallo di tempo tra le 1.00 e le 1.59.99 può essere interpretato come ora solare o ora legale. |
| Regola fissa      | Regola di rettifica che imposta una determinata data per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora legale all'ora solare che si verifica ogni anno il 25 ottobre segue una regola di rettifica fissa. |
| Regola mobile   | Regola di rettifica che imposta un determinato giorno di una determinata settimana di un determinato mese per la transizione alla o dall'ora legale. Ad esempio, una transizione dall'ora solare all'ora legale che si verifica la terza domenica del mese di marzo segue una regola di rettifica mobile. |
| Ora non valida    | Ora inesistente creata dalla transizione dall'ora solare all'ora legale. Si verifica quando l'orologio viene portato avanti, ad esempio durante la transizione dall'ora solare all'ora legale di un determinato fuso orario. Se ad esempio questa transizione ha luogo in un determinato giorno alle 2.00 e l'ora diventa le 3.00, ogni intervallo di tempo tra le 2.00 e le 2.59.99 non è valido. |
| Ora transizione | Informazioni su una modifica di ora specifica, ad esempio la modifica dall'ora legale all'ora solare o viceversa, in un particolare fuso orario. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Fusi orari e classe TimeZoneInfo

In .NET un <xref:System.TimeZoneInfo> oggetto rappresenta un fuso orario. La <xref:System.TimeZoneInfo> classe include un <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> metodo che restituisce una matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Ogni elemento di questa matrice fornisce informazioni sulla transizione da e verso l'ora legale per un determinato periodo di tempo. Per i fusi orari che non supportano l'ora legale, il metodo restituisce una matrice vuota. Ogni <xref:System.TimeZoneInfo.AdjustmentRule> oggetto dispone di un oggetto <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> e di una <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> proprietà che definisce la data e l'ora specifiche della transizione da e verso l'ora legale. La <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> proprietà indica se la transizione è fissa o mobile.

.NET si basa sulle informazioni sul fuso orario fornite dal sistema operativo Windows e memorizzate nel registro di sistema. A causa del numero di fusi orari della terra, non tutti i fusi orari esistenti sono rappresentati nel registro di sistema. Inoltre, poiché il registro di sistema è una struttura dinamica, i fusi orari predefiniti possono essere aggiunti o rimossi. Infine, il registro di sistema non contiene necessariamente i dati cronologici del fuso orario. Ad esempio, in Windows XP il registro di sistema contiene dati relativi a un singolo set di regolazioni del fuso orario. Windows Vista supporta i dati dinamici del fuso orario, il che significa che un singolo fuso orario può avere più regole di regolazione applicabili a intervalli di anni specifici. Tuttavia, la maggior parte dei fusi orari definiti nel registro di sistema di Windows Vista e supporta l'ora legale hanno solo una o due regole di regolazione predefinite.

La dipendenza della <xref:System.TimeZoneInfo> classe nel registro di sistema significa che un'applicazione in grado di riconoscere il fuso orario non può essere certo che un determinato fuso orario sia definito nel registro di sistema. Di conseguenza, se si prevede di creare un'istanza di un fuso orario specifico (diverso dal fuso orario locale o da quello che rappresenta l'ora UTC) è consigliabile usare la gestione delle eccezioni. Deve inoltre fornire un metodo per consentire all'applicazione di continuare se <xref:System.TimeZoneInfo> non è possibile creare un'istanza di un oggetto necessario dal registro di sistema.

Per gestire l'assenza di un fuso orario necessario, la <xref:System.TimeZoneInfo> classe include un <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo, che è possibile usare per creare fusi orari personalizzati che non sono stati trovati nel registro di sistema. Per informazioni dettagliate sulla creazione di un fuso orario personalizzato, vedere [procedura: creare fusi orari senza regole di rettifica](create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md). Inoltre, è possibile usare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per convertire un fuso orario appena creato in una stringa e salvarlo in un archivio dati, ad esempio un database, un file di testo, il registro di sistema o una risorsa dell'applicazione. È quindi possibile usare il <xref:System.TimeZoneInfo.FromSerializedString%2A> metodo per convertire nuovamente questa stringa in un <xref:System.TimeZoneInfo> oggetto. Per informazioni dettagliate, vedere [procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md).

Dato che ogni fuso orario è caratterizzato da un offset di base rispetto al fuso orario UTC, nonché da un offset da UTC che riflette eventuali regole di rettifica, un'ora in un fuso orario può essere convertita facilmente nell'ora corrispondente in un altro fuso orario. A questo scopo, l' <xref:System.TimeZoneInfo> oggetto include diversi metodi di conversione, tra cui:

- <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, che converte l'ora UTC nell'ora di un fuso orario designato.

- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, che converte l'ora in un fuso orario designato in ora UTC.

- <xref:System.TimeZoneInfo.ConvertTime%2A>, che converte l'ora in un fuso orario designato all'ora in un altro fuso orario designato.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, che usa gli identificatori del fuso orario (anziché <xref:System.TimeZoneInfo> gli oggetti) come parametri per convertire l'ora in un fuso orario designato all'ora in un altro fuso orario designato.

Per informazioni dettagliate sulla conversione degli orari tra fusi orari, vedere [Conversione degli orari tra fusi orari](converting-between-time-zones.md).

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
