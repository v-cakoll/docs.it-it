---
title: 'Procedura: creare fusi orari con regole di regolazione'
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
ms.openlocfilehash: c63b93e0dc587571605edb305979b8f97bf54cb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Procedura: creare fusi orari con regole di regolazione

Le informazioni di fuso orario preciso richiesto da un'applicazione potrebbero non essere presente in un determinato sistema per diversi motivi:

* Il fuso orario non è mai stato definito nel Registro di sistema del sistema locale.

* Dati sul fuso orario sono stati modificati o rimossi dal Registro di sistema.

* Il fuso orario non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo storico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile utilizzare l'overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con entrambe le regole di regolazione fissa o mobile. (Per le definizioni di questi termini, vedere la sezione "Terminologia fuso orario" in [Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Fusi orari personalizzati creati tramite la chiamata di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non vengono aggiunti al Registro di sistema. Ma è possibile accedervi solo tramite il riferimento all'oggetto restituito dal <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario con regole di regolazione. Per creare un fuso orario che non supporta regole di regolazione dell'ora legale, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Per creare un fuso orario con le regole di regolazione mobili

1. Per ogni nuova regolazione (che, per ogni transizione da e di nuovo all'ora solare in un intervallo di tempo specifico), eseguire le operazioni seguenti:

    1. Definire il tempo di transizione iniziale per la regolazione del fuso orario.

       È necessario chiamare il <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> (metodo) e passare un <xref:System.DateTime> valore che definisce il tempo di transizione, un valore intero che definisce il mese della transizione, un valore intero che definisce la settimana in cui si verifica la transizione, e un <xref:System.DayOfWeek> valore che definisce il giorno della settimana in cui si verifica la transizione. Crea un'istanza di questa chiamata al metodo un <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    2. Definire il tempo di transizione finale per la regolazione del fuso orario. Questa operazione richiede un'altra chiamata al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> metodo. Questa chiamata al metodo crea un'istanza di un secondo <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    3. Chiamare il <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> metodo e passarlo effettive di inizio e data di fine della regolazione, un <xref:System.TimeSpan> oggetto che definisce la quantità di tempo in cui la transizione e le due <xref:System.TimeZoneInfo.TransitionTime> oggetti che definiscono quando le transizioni da e verso legale ora si verificano. Crea un'istanza di questa chiamata al metodo un <xref:System.TimeZoneInfo.AdjustmentRule> oggetto.

    4. Assegnare il <xref:System.TimeZoneInfo.AdjustmentRule> oggetto a una matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti.

2. Definire nome visualizzato del fuso orario. Il nome visualizzato segue un formato pressoché standard in cui l'offset del fuso orario dall'ora Coordinated Universal Time (UTC) è racchiuso tra parentesi ed è seguito da una stringa che identifica il fuso orario, una o più delle città nel fuso orario, o in uno o più di cou Mo o aree del fuso orario.

3. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene utilizzata anche come identificatore del fuso orario.

4. Definire il nome dell'ora legale del fuso orario.

5. Se si desidera utilizzare un identificatore nome standard del fuso orario diverso, definire l'identificatore del fuso orario.

6. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario dall'ora UTC. Fusi orari con ore in avanti rispetto all'ora UTC hanno un offset positivo. Fusi orari con ore precedenti rispetto all'ora UTC hanno un offset negativo.

7. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

L'esempio seguente definisce un fuso orario centrale Standard per gli Stati Uniti che include le regole di regolazione per un'ampia gamma di intervalli di tempo da 1918 a quella corrente.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Il fuso orario creato in questo esempio dispone di più regole di regolazione. È necessario pertanto verificare che le date di inizio e data di fine di qualsiasi regola di rettifica non si sovrapponga con le date di un'altra regola di rettifica. Se è presente una sovrapposizione, un <xref:System.InvalidTimeZoneException> viene generata un'eccezione.

Per le regole di regolazione mobili, il valore 5 viene passato per il `week` parametro il <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo per indicare che la transizione si verifica nell'ultima settimana di un determinato mese.

Nella creazione della matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti da utilizzare nella <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> chiamata al metodo, il codice può inizializzare la matrice per la dimensione della richiesta per il numero di modifiche da creare per il fuso orario. Al contrario, questo codice di esempio chiama il <xref:System.Collections.Generic.List%601.Add%2A> metodo per aggiungere ogni regola di rettifica per un oggetto generico <xref:System.Collections.Generic.List%601> insieme di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Il codice chiama quindi il <xref:System.Collections.Generic.List%601.CopyTo%2A> metodo per copiare i membri di questa raccolta nella matrice.

Nell'esempio viene inoltre utilizzata la <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> metodo per definire regolazioni a data fissa. Questa operazione è simile alla chiamata di <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo, ad eccezione del fatto che richiede solo l'ora, mese e giorno parametri di transizione.

L'esempio è possibile verificarlo utilizzando codice analogo al seguente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Un riferimento a System.Core.dll essere aggiunto al progetto.

* Che importati spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md)
[procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
