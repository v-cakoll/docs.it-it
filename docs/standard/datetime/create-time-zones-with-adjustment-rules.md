---
title: 'Procedura: creare fusi orari con regole di rettifica'
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
ms.openlocfilehash: b7e938581dfde3f1566aa2506302292686c2fc5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278168"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Procedura: creare fusi orari con regole di rettifica

Le informazioni esatte sul fuso orario richieste da un'applicazione potrebbero non essere presenti in un sistema specifico per diversi motivi:

- Il fuso orario non è mai stato definito nel registro di sistema del sistema locale.

- I dati relativi al fuso orario sono stati modificati o rimossi dal registro di sistema.

- Il fuso orario non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo cronologico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile usare gli overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con regole di rettifica fisse o mobili. Per le definizioni di questi termini, vedere la sezione "terminologia del fuso orario" nella [Panoramica del fuso orario](time-zone-overview.md).

> [!IMPORTANT]
> I fusi orari personalizzati creati chiamando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo non vengono aggiunti al registro di sistema. Al contrario, è possibile accedervi solo tramite il riferimento all'oggetto restituito dalla <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario con regole di rettifica. Per creare un fuso orario che non supporta le regole di regolazione dell'ora legale, vedere [procedura: creare fusi orari senza regole di regolazione](create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Per creare un fuso orario con regole di rettifica a virgola mobile

1. Per ogni regolazione, ovvero per ogni transizione da e verso l'ora solare in un intervallo di tempo specifico, procedere come segue:

    1. Definire il tempo di transizione iniziale per la regolazione del fuso orario.

       È necessario chiamare il <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> metodo e passargli un <xref:System.DateTime> valore che definisce l'ora della transizione, un valore intero che definisce il mese della transizione, un valore intero che definisce la settimana in cui si verifica la transizione e un <xref:System.DayOfWeek> valore che definisce il giorno della settimana in cui si verifica la transizione. Questa chiamata al metodo crea un'istanza di un <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    2. Definire il tempo di transizione finale per la regolazione del fuso orario. Questa operazione richiede un'altra chiamata al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> metodo. Questa chiamata al metodo crea un'istanza di un secondo <xref:System.TimeZoneInfo.TransitionTime> oggetto.

    3. Chiamare il <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> metodo e passare le date di inizio e di fine valide della regolazione, un <xref:System.TimeSpan> oggetto che definisce la quantità di tempo nella transizione e i due <xref:System.TimeZoneInfo.TransitionTime> oggetti che definiscono quando si verificano le transizioni da e verso l'ora legale. Questa chiamata al metodo crea un'istanza di un <xref:System.TimeZoneInfo.AdjustmentRule> oggetto.

    4. Assegnare l' <xref:System.TimeZoneInfo.AdjustmentRule> oggetto a una matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti.

2. Definire il nome visualizzato del fuso orario. Il nome visualizzato segue un formato abbastanza standard in cui l'offset del fuso orario rispetto all'ora UTC (Coordinated Universal Time) è racchiuso tra parentesi ed è seguito da una stringa che identifica il fuso orario, una o più città del fuso orario o uno o più paesi o aree del fuso orario.

3. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene usata anche come identificatore del fuso orario.

4. Definire il nome dell'ora legale del fuso orario.

5. Se si vuole usare un identificatore diverso dal nome standard del fuso orario, definire l'identificatore del fuso orario.

6. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario rispetto all'ora UTC. I fusi orari con tempi successivi all'ora UTC hanno un offset positivo. I fusi orari con tempi precedenti all'ora UTC hanno un offset negativo.

7. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

Nell'esempio seguente viene definito un fuso orario standard centrale per la Stati Uniti che include regole di rettifica per un'ampia gamma di intervalli di tempo da 1918 al momento corrente.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Il fuso orario creato in questo esempio include più regole di regolazione. È necessario prestare attenzione per assicurarsi che le date di inizio e di fine valide di una regola di rettifica non si sovrappongano alle date di un'altra regola di rettifica. Se si verifica una sovrapposizione, <xref:System.InvalidTimeZoneException> viene generata un'eccezione.

Per le regole di rettifica a virgola mobile, il valore 5 viene passato al `week` parametro del <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo per indicare che la transizione si verifica nell'ultima settimana di un determinato mese.

Quando si crea la matrice di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti da usare nella <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> chiamata al metodo, il codice potrebbe inizializzare la matrice in base alla dimensione richiesta dal numero di modifiche da creare per il fuso orario. Al contrario, in questo esempio di codice viene chiamato il <xref:System.Collections.Generic.List%601.Add%2A> metodo per aggiungere ogni regola di regolazione a una raccolta generica <xref:System.Collections.Generic.List%601> di <xref:System.TimeZoneInfo.AdjustmentRule> oggetti. Il codice chiama quindi il <xref:System.Collections.Generic.List%601.CopyTo%2A> metodo per copiare i membri di questa raccolta nella matrice.

Nell'esempio viene inoltre usato il <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> metodo per definire le regolazioni a data fissa. Questa operazione è simile alla chiamata al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> metodo, con la differenza che richiede solo l'ora, il mese e il giorno dei parametri di transizione.

L'esempio può essere testato usando un codice simile al seguente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che vengano importati gli spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Panoramica sul fuso orario](time-zone-overview.md)
- [Procedura: creare fusi orari senza regole di regolazione](create-time-zones-without-adjustment-rules.md)
