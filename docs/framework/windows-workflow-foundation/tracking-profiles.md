---
title: Profili di rilevamento
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 9723b8fbb0bb8f24e8c9544d8bac8252b2fc763a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182733"
---
# <a name="tracking-profiles"></a>Profili di rilevamento

I profili di rilevamento contengono query di rilevamento che consentono a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro creati quando lo stato di un'istanza del flusso di lavoro viene modificato in fase di esecuzione.

## <a name="tracking-profiles"></a>Profili di rilevamento

I profili di rilevamento vengono usati per specificare le informazioni di rilevamento generate per un'istanza del flusso di lavoro. Se non è specificato alcun profilo, vengono generati tutti gli eventi di rilevamento. Se viene specificato un profilo, verranno generati gli eventi di rilevamento specificati nel profilo. A seconda dei requisiti di monitoraggio, è possibile scrivere un profilo molto generale che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro oppure creare un profilo molto dettagliato i cui eventi risultanti sono sufficientemente precisi per ricostruire un flusso di esecuzione dettagliato in un secondo momento.

I profili di rilevamento si manifestano come elementi XML all'interno di un file di configurazione .NET Framework standard o specificati nel codice. Nell'esempio seguente è illustrato un profilo di rilevamento di [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] in un file di configurazione che consente a un partecipante del rilevamento di sottoscrivere gli eventi del flusso di lavoro `Started` e `Completed`.

```xml
<system.serviceModel>
    ...
    <tracking>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started"/>
                <state name="Completed"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
    ...
</system.serviceModel>
```

Nell'esempio seguente viene illustrato il profilo di rilevamento equivalente creato usando il codice.

```csharp
TrackingProfile profile = new TrackingProfile()
{
    Name = "CustomTrackingProfile",
    Queries =
    {
        new WorkflowInstanceQuery()
        {
            // Limit workflow instance tracking records for started and
            // completed workflow states.
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },
        }
    }
};
```

I record di rilevamento vengono filtrati tramite la modalità di visibilità all'interno di un profilo di rilevamento usando l'attributo <xref:System.Activities.Tracking.ImplementationVisibility>. Un'attività composita è un'attività di primo livello che contiene le altre attività che formano l'implementazione. La modalità di visibilità specifica i record di rilevamento creati dalle attività composite all'interno di un'attività di flusso di lavoro per specificare se le attività che formano l'implementazione vengono rilevate. La modalità di visibilità si applica a livello del profilo di rilevamento. L'applicazione di filtri ai record di rilevamento per singole attività all'interno di un flusso di lavoro viene controllata dalle query incluse nel profilo di rilevamento. Per altre informazioni, vedere la sezione Tipi di query del profilo di **rilevamento** in questo documento.

Le due modalità di visibilità specificate dall'attributo `implementationVisibility` nel profilo di rilevamento sono: `RootScope` e `All`. Usando la modalità `RootScope` vengono eliminati i record di rilevamento per le attività che formano l'implementazione di un'attività nel caso in cui un'attività composita non costituisca la radice di un flusso di lavoro. Di conseguenza, quando un'attività implementata tramite altre attività viene aggiunta a un flusso di lavoro e l'attributo `implementationVisibility` viene impostato su RootScope, viene rilevata solo l'attività di primo livello all'interno di tale attività composita. Se un'attività costituisce la radice del flusso di lavoro, l'implementazione dell'attività è il flusso di lavoro stesso e i record di rilevamento vengono creati per le attività che formano l'implementazione. Tramite la modalità All, tutti i record di rilevamento possono essere creati per l'attività radice e tutte le relative attività composite.

Si supponga, ad esempio, *MyActivity* è un'attività composita la cui implementazione contiene due attività, *Activity1* e *Activity2*. Quando questa attività viene aggiunta a un flusso di `implementationVisibility` lavoro `RootScope`e il rilevamento viene abilitato con un profilo di rilevamento impostato su , i record di rilevamento vengono generati solo per *MyActivity*. Tuttavia, non vengono generati record per le attività *Activity1* e *Activity2*.

Tuttavia, `implementationVisibility` se l'attributo per `All`il profilo di rilevamento è impostato su , i record di rilevamento vengono generati non solo per *MyActivity*, ma anche per le attività *Activity1* e *Activity2*.

Il flag `implementationVisibility` si applica ai seguenti tipi di record di rilevamento:

- ActivityStateRecord

- FaultPropagationRecord

- CancelRequestedRecord

- ActivityScheduledRecord

> [!NOTE]
> I record CustomTrackingRecords creati dall'implementazione di attività non vengono filtrati dall'impostazione implementationVisibility.

La funzionalità `implementationVisibility` viene specificata come <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> nel profilo di rilevamento nel codice come riportato di seguito:

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

La funzionalità `implementationVisibility` è specificata come <xref:System.Activities.Tracking.ImplementationVisibility.All> nel profilo di rilevamento in un file di configurazione come riportato di seguito:

```xml
<tracking>
      <profiles>
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">
          <workflow activityDefinitionId="*">
...
         </workflow>
        </trackingProfile>
      </profiles>
</tracking>
```

L'impostazione `ImplementationVisibility` nel profilo di rilevamento è facoltativa. Per impostazione predefinita, il relativo valore è impostato su `RootScope`. Per i valori di questo attributo viene applicata la distinzione tra maiuscole e minuscole.

### <a name="tracking-profile-query-types"></a>Tipi di query del profilo di rilevamento

I profili di rilevamento vengono strutturati sotto forma di sottoscrizioni dichiarative per record di rilevamento che consentono di eseguire query sulla fase di esecuzione del flusso di lavoro per record di rilevamento specifici. Sono disponibili numerosi tipi di query che consentono di sottoscrivere classi differenti di oggetti <xref:System.Activities.Tracking.TrackingRecord>. I profili di rilevamento possono essere specificati nella configurazione o tramite codice. Di seguito sono riportati i tipi di query più comuni:

- <xref:System.Activities.Tracking.WorkflowInstanceQuery>: usare questo tipo per rilevare le modifiche del ciclo di vita dell'istanza del flusso di lavoro, ad esempio gli eventi `Started` e `Completed` dimostrati precedentemente. L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  Gli stati disponibili per la sottoscrizione sono specificati nella classe <xref:System.Activities.Tracking.WorkflowInstanceStates>.

  La configurazione o il codice usato per sottoscrivere i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando l'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> è illustrato nell'esempio seguente.

  ```xml
  <workflowInstanceQueries>
      <workflowInstanceQuery>
        <states>
          <state name="Started"/>
        </states>
      </workflowInstanceQuery>
  </workflowInstanceQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new WorkflowInstanceQuery()
          {
              States = { WorkflowInstanceStates.Started}
          }
      }
  };
  ```

- <xref:System.Activities.Tracking.ActivityStateQuery>: usare questo tipo per rilevare le modifiche del ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro. Ad esempio, è possibile tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata all'interno di un'istanza del flusso di lavoro. Questa query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.ActivityStateRecord>. Gli stati disponibili per la sottoscrizione sono specificati nell'oggetto <xref:System.Activities.Tracking.ActivityStates>.

  La configurazione e il codice usati per sottoscrivere i record di rilevamento dello stato dell'attività che usano l'oggetto <xref:System.Activities.Tracking.ActivityStateQuery> per l'attività `SendEmailActivity` sono illustrati nell'esempio seguente.

  ```xml
  <activityStateQueries>
    <activityStateQuery activityName="SendEmailActivity">
      <states>
        <state name="Closed"/>
      </states>
    </activityStateQuery>
  </activityStateQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityStateQuery()
          {
              ActivityName = "SendEmailActivity",
              States = { ActivityStates.Closed }
          }
      }
  };
  ```

  > [!NOTE]
  > Se più elementi activityStateQuery hanno lo stesso nome, solo gli stati nell'ultimo elemento vengono usati nel profilo di rilevamento.

- <xref:System.Activities.Tracking.ActivityScheduledQuery>: questa query consente di rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre. La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.ActivityScheduledRecord>.

  La configurazione e il codice usati per sottoscrivere i record relativi all'attività figlio `SendEmailActivity` in fase di pianificazione tramite l'oggetto <xref:System.Activities.Tracking.ActivityScheduledQuery> sono illustrati nell'esempio seguente.

  ```xml
  <activityScheduledQueries>
    <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </activityScheduledQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityScheduledQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <xref:System.Activities.Tracking.FaultPropagationQuery>: usare questo tipo per rilevare la gestione degli errori che si verificano all'interno di un'attività. La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.FaultPropagationRecord>.

  La configurazione e il codice usati per sottoscrivere i record relativi alla propagazione degli errori tramite l'oggetto <xref:System.Activities.Tracking.FaultPropagationQuery> sono illustrati nell'esempio seguente.

  ```xml
  <faultPropagationQueries>
    <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />
  </faultPropagationQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new FaultPropagationQuery()
          {
              FaultSourceActivityName = "SendEmailActivity",
              FaultHandlerActivityName = "NotificationsFaultHandler"
          }
      }
  };
  ```

- <xref:System.Activities.Tracking.CancelRequestedQuery>: usare questo tipo per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre. La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.CancelRequestedRecord>.

  La configurazione e il codice utilizzati per <xref:System.Activities.Tracking.CancelRequestedQuery> sottoscrivere i record correlati all'annullamento dell'attività tramite è illustrato nell'esempio seguente.

  ```xml
  <cancelRequestedQueries>
    <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </cancelRequestedQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CancelRequestedQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <xref:System.Activities.Tracking.CustomTrackingQuery>: usare questo tipo per rilevare gli eventi definiti nelle attività del codice. La query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.CustomTrackingRecord>.

  La configurazione e il codice usati per sottoscrivere i record relativi ai record di rilevamento personalizzati tramite l'oggetto <xref:System.Activities.Tracking.CustomTrackingQuery> sono illustrati nell'esempio seguente.

  ```xml
  <customTrackingQueries>
    <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />
  </customTrackingQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CustomTrackingQuery()
          {
              Name = "EmailAddress",
              ActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <xref:System.Activities.Tracking.BookmarkResumptionQuery>: usare questo tipo per rilevare la ripresa di un segnalibro all'interno di un'istanza del flusso di lavoro. Questa query è necessaria affinché un oggetto <xref:System.Activities.Tracking.TrackingParticipant> sottoscriva gli oggetti <xref:System.Activities.Tracking.BookmarkResumptionRecord>.

  La configurazione e il codice usati per sottoscrivere i record relativi alla ripresa del segnalibro tramite l'oggetto <xref:System.Activities.Tracking.BookmarkResumptionQuery> sono illustrati nell'esempio seguente.

  ```xml
  <bookmarkResumptionQueries>
    <bookmarkResumptionQuery name="SentEmailBookmark" />
  </bookmarkResumptionQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new BookmarkResumptionQuery()
          {
              Name = "sentEmailBookmark"
          }
      }
  };
  ```

### <a name="annotations"></a>annotazioni

Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione. Ad esempio, è possibile che si desideri che diversi record di rilevamento in più flussi di lavoro vengano contrassegnati con "Server di posta elettronica" . Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.

A tal fine, viene aggiunta un'annotazione a una query di rilevamento come mostrato nell'esempio seguente.

```xml
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed"/>
  </states>
  <annotations>
    <annotation name="MailServer" value="Mail Server1"/>
  </annotations>
</activityStateQuery>
```

### <a name="how-to-create-a-tracking-profile"></a>Come creare un profilo di rilevamento

Gli elementi di query di rilevamento vengono utilizzati [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] per creare un profilo di rilevamento usando un codice o un file di configurazione XML. Di seguito è riportato un esempio di un profilo di rilevamento creato usando un file di configurazione.

```xml
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile ">
        <workflow activityDefinitionId="*">
          <!--Specify the tracking profile query elements to subscribe for tracking records-->
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```

> [!WARNING]
> Per un servizio WF in cui viene usato l'host del servizio del flusso di lavoro, il profilo di rilevamento viene generalmente creato usando un file di configurazione. È anche possibile creare un profilo di rilevamento con il codice, usando il profilo di rilevamento e l'API della query di rilevamento.

Un profilo configurato come file di configurazione XML viene applicato a un partecipante del rilevamento tramite un'estensione di comportamento. Questo viene aggiunto a un oggetto WorkflowServiceHost come descritto nella sezione successiva [Configurazione del rilevamento per un flusso di lavoro](configuring-tracking-for-a-workflow.md).

Il livello di dettaglio dei record di rilevamento creati dall'host è determinato dalle impostazioni di configurazione all'interno del profilo di rilevamento. Un partecipante del rilevamento sottoscrive i record di rilevamento aggiungendo query a un profilo di rilevamento. Per sottoscrivere tutti i record di rilevamento, il\*profilo di rilevamento deve specificare tutte le query di rilevamento utilizzando " " nei campi del nome in ognuna delle query.

Di seguito sono riportati alcuni degli esempi comuni di profili di rilevamento.

- Profilo di rilevamento per ottenere i record dell'istanza del flusso di lavoro e gli errori.

  ```xml
  <trackingProfile name="Instance and Fault Records">
    <workflow activityDefinitionId="*">
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="*" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
      <activityStateQueries>
        <activityStateQuery activityName="*">
          <states>
            <state name="Faulted"/>
          </states>
        </activityStateQuery>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
  ```

- Profilo di rilevamento per ottenere tutti i record di rilevamento personalizzati.

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a>Vedere anche

- [Rilevamento SQL](./samples/sql-tracking.md)
- [Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitoraggio delle applicazioni con App FabricMonitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
