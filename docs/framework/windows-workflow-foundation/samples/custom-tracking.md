---
title: Rilevamento personalizzato
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 2b100b877bbc8c6d830f09a4a59decffde511511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182846"
---
# <a name="custom-tracking"></a>Rilevamento personalizzato
Nell'esempio viene illustrato come creare un partecipante di rilevamento personalizzato e scrivere il contenuto dei dati di rilevamento nella console. Nell'esempio viene inoltre illustrato come generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> popolati con dati definiti dall'utente. Il partecipante di rilevamento basato su console filtra gli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati dal flusso di lavoro usando un oggetto profilo di rilevamento creato nel codice.

## <a name="sample-details"></a>Dettagli dell'esempio
 Windows Workflow Foundation (WF) fornisce un'infrastruttura di rilevamento per tenere traccia dell'esecuzione di un'istanza del flusso di lavoro. Il runtime di rilevamento implementa un'istanza del flusso di lavoro per generare eventi correlati al ciclo di vita del flusso di lavoro, eventi da attività del flusso di lavoro ed eventi personalizzati. Nella tabella seguente sono indicati in dettaglio i componenti primari dell'infrastruttura di rilevamento.

|Componente|Descrizione|
|---------------|-----------------|
|Esecuzione del rilevamento|Fornisce l'infrastruttura per la creazione dei record di rilevamento.|
|Partecipanti del rilevamento|Usa i record di rilevamento. .NET Framework 4 viene fornito con un partecipante di rilevamento che scrive i record di rilevamento come eventi ETW (Event Tracing for Windows).|
|Profilo di rilevamento|Meccanismo di filtro che consente a un partecipante del rilevamento di sottoscrivere un subset dei record di rilevamento creati da un'istanza del flusso di lavoro.|

 Nella tabella seguente vengono indicati in dettaglio i record di rilevamento creati dall'esecuzione del flusso di lavoro.

|Record di rilevamento|Descrizione|
|---------------------|-----------------|
|Record di rilevamento dell'istanza del flusso di lavoro.|Descrivono il ciclo di vita dell'istanza del flusso di lavoro. Ad esempio un record di istanza viene creato quando viene avviato o completato il flusso di lavoro.|
|Record di rilevamento dello stato dell'attività.|Illustrano in dettaglio l'esecuzione dell'attività. Questi record indicano lo stato di un'attività del flusso di lavoro, ad esempio quando un'attività viene pianificata, quando viene completata o quando viene generato un errore.|
|Record di ripresa del segnalibro.|Generato quando viene ripreso un segnalibro all'interno di un'istanza del flusso di lavoro.|
|Record di rilevamento personalizzati.|Un autore del flusso di lavoro può creare record di rilevamento personalizzati e generarli all'interno dell'attività personalizzata.|

 Il partecipante di rilevamento sottoscrive un subset degli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati usando profili di rilevamento. Un profilo di rilevamento contiene query di rilevamento che consentono la sottoscrizione di un particolare tipo di record di rilevamento. I profili di rilevamento possono essere specificati nel codice o nella configurazione.

### <a name="custom-tracking-participant"></a>Partecipante di rilevamento personalizzato
 L'API del partecipante di rilevamento consente l'estensione del runtime di rilevamento con un partecipante di rilevamento fornito dall'utente, che può includere la logica personalizzata per gestire gli oggetti <xref:System.Activities.Tracking.TrackingRecord> generati dall'esecuzione del flusso di lavoro.

 Per scrivere un partecipante di rilevamento l'utente deve implementare <xref:System.Activities.Tracking.TrackingParticipant>. In particolare, il metodo <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> deve essere implementato dal partecipante personalizzato. Questo metodo viene chiamato quando un oggetto <xref:System.Activities.Tracking.TrackingRecord> viene generato dall'esecuzione del flusso di lavoro.

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 Il partecipante di rilevamento completo viene implementato nel file di ConsoleTrackingParticipant.cs. L'esempio di <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> codice seguente è il metodo per il partecipante del rilevamento personalizzato.

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 Nell'esempio di codice seguente viene aggiunto il partecipante della console all'oggetto invoker del flusso di lavoro.

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a>Creazione di record di rilevamento personalizzati
 In questo esempio viene inoltre illustrata la possibilità di generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> da un'attività flusso di lavoro personalizzata:

- Gli oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> vengono creati e popolati con dati definiti dall'utente che si desidera vengano generati con il record.

- L'oggetto <xref:System.Activities.Tracking.CustomTrackingRecord> viene generato chiamando il <xref:System.Activities.ActivityContext>metodo track dell'oggetto .

 Nell'esempio seguente viene illustrato come generare oggetti <xref:System.Activities.Tracking.CustomTrackingRecord> all'interno di un'attività personalizzata.

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Utilizzando Visual Studio 2010, aprire il file di soluzione CustomTrackingSample.sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere CTRL+F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
