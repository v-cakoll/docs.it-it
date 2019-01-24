---
title: 'Procedura: Creare fusi orari con regole di regolazione'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83905c97f37a0e49f6219da47e2f640ecfb8edfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721175"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Procedura: Creare fusi orari con regole di regolazione

Le informazioni del fuso orario preciso richiesto da un'applicazione potrebbero non essere presente in un sistema specifico per diversi motivi:

* Il fuso orario non è mai stato definito nel Registro di sistema locale.

* I dati sul fuso orario sono stati modificati o rimossi dal Registro di sistema.

* Il fuso orario non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo storico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile usare gli overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con entrambe le regole di rettifica fissa o mobile. (Per le definizioni di questi termini, vedere la sezione "Terminologia fuso orario" nella [Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Fusi orari personalizzati creati tramite la chiamata di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non vengono aggiunti al Registro di sistema. Al contrario, è possibile accedervi solo tramite il riferimento all'oggetto restituito dal <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario con regole di regolazione. Per creare un fuso orario che non supporta regole di regolazione dell'ora legale, vedere [come: Creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Per creare un fuso orario con regole di rettifica mobili

1. Per ogni transizione (che è, per ogni transizione da e verso l'ora solare in un intervallo di tempo specifico), eseguire le operazioni seguenti:

    1. Definire il tempo di transizione iniziale per la regolazione del fuso orario.

       È necessario chiamare il <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> metodo e passare un <xref:System.DateTime> valore che definisce il tempo di transizione, valore integer che definisce il mese della transizione, valore integer che definisce la settimana in cui si verifica la transizione, e un <xref:System.DayOfWeek> valore che definisce il giorno della settimana in cui si verifica la transizione. Crea un'istanza di questa chiamata al metodo un <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    2. Definire il tempo di transizione finale per la regolazione del fuso orario. Questa operazione richiede un'altra chiamata al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> (metodo). Questa chiamata al metodo crea un'istanza di un secondo <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    3. Chiamare il <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> (metodo) e passarlo efficace date di inizio e fine di regolazione, un' <xref:System.TimeSpan> che definisce la quantità di tempo di transizione e le due <xref:System.TimeZoneInfo.TransitionTime> oggetti che definiscono quando le transizioni da e verso legale ora si verificano. Crea un'istanza di questa chiamata al metodo un <xref:System.TimeZoneInfo.AdjustmentRule> oggetto.

    4. Assegnare il <xref:System.TimeZoneInfo.AdjustmentRule> a una matrice di oggetti <xref:System.TimeZoneInfo.AdjustmentRule> oggetti.

2. Definire nome visualizzato del fuso orario. Il nome visualizzato segue un formato piuttosto standard in cui è racchiuso tra parentesi offset del fuso orario dall'ora Coordinated Universal Time (UTC) ed è seguito da una stringa che identifica il fuso orario, una o più delle città nel fuso orario o uno più il cou Mo o aree geografiche nel fuso orario.

3. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene utilizzata anche come identificatore del fuso orario.

4. Definire il nome dell'ora legale del fuso orario.

5. Se si desidera usare un identificatore differente rispetto al nome del fuso orario standard, definire l'identificatore del fuso orario.

6. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario rispetto all'ora UTC. Fusi orari con volte in cui siano successivi rispetto all'ora UTC avere un offset positivi. Fusi orari con ore indietro rispetto all'ora UTC hanno una differenza negativa.

7. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

L'esempio seguente definisce un fuso orario Standard centrale degli Stati Uniti che include le regole di regolazione per un'ampia gamma di intervalli di tempo da 1918 a quella attuale.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Il fuso orario creato in questo esempio include più regole di regolazione. Prestare attenzione per assicurarsi che l'efficace date di inizio e fine di qualsiasi regola di rettifica non si sovrappongono con le date di un'altra regola di rettifica. Se è presente una sovrapposizione, un <xref:System.InvalidTimeZoneException> viene generata un'eccezione.

Per le regole di rettifica mobili, il valore 5 viene passato per il `week` parametro del <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo per indicare che la transizione si verifica nell'ultima settimana di un determinato mese.

Nella creazione della matrice di <xref:System.TimeZoneInfo.AdjustmentRule> degli oggetti da utilizzare nel <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> chiamata al metodo, il codice è stato possibile inizializzare la matrice per le dimensioni richieste per il numero di modifiche deve essere creato per il fuso orario. Questo esempio di codice, chiama il <xref:System.Collections.Generic.List%601.Add%2A> metodo per aggiungere ogni regola di rettifica generico <xref:System.Collections.Generic.List%601> insieme di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Il codice chiama quindi il <xref:System.Collections.Generic.List%601.CopyTo%2A> metodo per copiare i membri di questa raccolta nella matrice.

L'esempio Usa anche il <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> metodo per definire le regolazioni data fissa. Ciò è simile alla chiamata di <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo, ad eccezione del fatto che richiede solo l'ora, mese e giorno dei parametri di transizione.

L'esempio può essere testato usando codice simile al seguente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Aggiungere un riferimento a DLL al progetto.

* Che siano importati spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
- [Procedura: Creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
