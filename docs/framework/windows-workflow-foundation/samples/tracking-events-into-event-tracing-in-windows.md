---
title: Eventi di rilevamento in Traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: f812659b-0943-45ff-9430-4defa733182b
ms.openlocfilehash: 6384c74aa245db490d04fa95f37bd860dfb9bad9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166530"
---
# <a name="tracking-events-into-event-tracing-in-windows"></a>Eventi di rilevamento in Traccia eventi per Windows
In questo esempio viene illustrato come abilitare la traccia in un servizio del flusso di lavoro Windows Workflow Foundation (WF) e creare gli eventi di rilevamento in Event Tracing for Windows (ETW). Per creare record di rilevamento del flusso di lavoro in ETW, nell'esempio viene usato il partecipante del rilevamento ETW (<xref:System.Activities.Tracking.EtwTrackingParticipant>).

 Il flusso di lavoro nell'esempio riceve una richiesta, assegna il reciproco dei dati di input alla variabile di input e restituisce di nuovo il reciproco al client. Quando i dati di input sono pari a 0, si verifica un'eccezione di divisione per zero non gestita che causa l'interruzione del flusso di lavoro. Con il rilevamento abilitato, il record di rilevamento errori viene creato in ETW consentendo la risoluzione dell'errore in un secondo momento. Il partecipante del rilevamento ETW viene configurato con un profilo di rilevamento per sottoscrivere i record di rilevamento. Il profilo di rilevamento viene definito nel file Web.config e fornito come parametro di configurazione al partecipante del rilevamento ETW. Quest'ultimo viene configurato nel file Web.config del servizio flusso di lavoro e viene applicato al servizio come comportamento del servizio. In questo esempio gli eventi di rilevamento vengono visualizzati nel registro eventi tramite Visualizzatore eventi.

## <a name="workflow-tracking-details"></a>Dettagli relativi al rilevamento del flusso di lavoro
 Windows Workflow Foundation fornisce un'infrastruttura di rilevamento per tenere traccia dell'esecuzione di un'istanza del flusso di lavoro. L'esecuzione del rilevamento crea un'istanza del flusso di lavoro per generare eventi correlati al ciclo di vita del flusso di lavoro, eventi dalle attività del flusso di lavoro ed eventi personalizzati. Nella tabella seguente sono indicati in dettaglio i componenti primari dell'infrastruttura di rilevamento.

|Componente|Descrizione|
|---------------|-----------------|
|Esecuzione del rilevamento|Fornisce l'infrastruttura per la creazione dei record di rilevamento.|
|Partecipanti del rilevamento|Accede ai record di rilevamento. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] viene fornito con un partecipante del rilevamento che scrive record di rilevamento come eventi di Event Tracing for Windows (ETW).|
|Profilo di rilevamento|Meccanismo di filtro che consente a un partecipante del rilevamento di sottoscrivere un subset dei record di rilevamento creati da un'istanza del flusso di lavoro.|

 Nella tabella seguente vengono indicati in dettaglio i record di rilevamento creati dall'esecuzione del flusso di lavoro.

|Record di rilevamento|Descrizione|
|---------------------|-----------------|
|Record di rilevamento dell'istanza del flusso di lavoro.|Descrivono il ciclo di vita dell'istanza del flusso di lavoro. Ad esempio un record di istanza viene creato quando viene avviato o completato il flusso di lavoro.|
|Record di rilevamento dello stato dell'attività.|Illustrano in dettaglio l'esecuzione dell'attività. Questi record indicano lo stato di un'attività del flusso di lavoro, ad esempio quando un'attività viene pianificata, quando viene completata o quando viene generato un errore.|
|Record di ripresa del segnalibro.|Generato quando viene ripreso un segnalibro all'interno di un'istanza del flusso di lavoro.|
|Record di rilevamento personalizzati.|Un autore del flusso di lavoro può creare record di rilevamento personalizzati e generarli all'interno dell'attività personalizzata.|
|<xref:System.Activities.Tracking.ActivityScheduledRecord>|Questo record viene creato quando un'attività pianifica un'altra attività.|
|<xref:System.Activities.Tracking.FaultPropagationRecord>|Questo record viene creato quando un errore viene propagato da un'attività.|
|<xref:System.Activities.Tracking.CancelRequestedRecord>|Questo record viene creato quando un'attività viene annullata da un'altra attività.|

 Il partecipante del rilevamento sottoscrive un subset dei record di rilevamento creati usando profili di rilevamento. Un profilo di rilevamento contiene query di rilevamento che consentono la sottoscrizione di un particolare tipo di record di rilevamento. I profili di rilevamento possono essere specificati nel codice o nella configurazione.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Con Visual Studio 2010, aprire il file della soluzione Etwtrackingparticipantsample.

2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

3.  Per eseguire la soluzione, premere F5.

     Per impostazione predefinita, il servizio è in ascolto sulla porta 53797 (http://localhost:53797/SampleWorkflowService.xamlx).

4.  Usando [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], aprire il client di WCF.

     Il client di prova WCF (WcfTestClient.exe) si trova nel \<cartella di installazione di Visual Studio 2010 > cartella \Common7\IDE\.

     La cartella di installazione di Visual Studio 2010 predefinita è c:\Programmi\Microsoft Visual Studio 10.0.

5.  Nel client di prova WCF selezionare **aggiunta di un servizio** dalle **File** menu.

     Aggiungere l'indirizzo dell'endpoint nella casella di input. Il valore predefinito è `http://localhost:53797/SampleWorkflowService.xamlx`.

6.  Aprire l'applicazione Visualizzatore eventi.

     Prima di richiamare il servizio, avviare Visualizzatore eventi dal **avviare** dal menu **eseguito** e digitare `eventvwr.exe`. Assicurarsi che il registro eventi sia in ascolto di eventi di rilevamento creati dal servizio flusso di lavoro.

7.  Nella visualizzazione albero del Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, e **Microsoft**. Fare doppio clic su **Microsoft** e selezionare **View** e quindi **Visualizza registri analitici e Debug** per abilitare l'analisi e i registri di debug

     Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata.

8.  Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Attiva registro** per abilitare il **analitico** log.

9. Eseguire il test del servizio tramite il client di prova WCF facendo doppio clic su `GetData`.

     Verrà visualizzato il metodo `GetData`. La richiesta accetta un parametro e assicura che il valore sia 0, ovvero l'impostazione predefinita.

     Fare clic su **richiamare**.

10. Osservare gli eventi creati dal flusso di lavoro.

     Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **aggiornare**.

     Gli eventi del flusso di lavoro vengono visualizzati nel visualizzatore eventi. Si noti che vengono visualizzati gli eventi di esecuzione del flusso di lavoro e che uno di questi è un'eccezione non gestita che corrisponde all'errore nel flusso di lavoro. Inoltre, viene creato un evento di avviso dall'attività del flusso di lavoro indicante che l'attività sta generando un errore.

11. Ripetere i passaggi 9 e 10 con un input di dati diverso da 0, in modo che non venga generato alcun errore.

 I profili di rilevamento consentono di sottoscrivere gli eventi creati dall'esecuzione quando lo stato di un'istanza del flusso di lavoro viene modificato. A seconda dei requisiti di monitoraggio, è possibile creare un profilo molto generico che sottoscrive un piccolo set di modifiche dello stato di alto livello in un flusso di lavoro. D'altra parte, è possibile creare un profilo molto preciso il cui output è dettagliato abbastanza per ricostruire l'esecuzione in un secondo momento. Nell'esempio vengono illustrati gli eventi creati dall'esecuzione del flusso di lavoro in ETW usando l'oggetto `HealthMonitoring Tracking Profile` che crea un piccolo set di eventi. Un profilo diverso che crea più eventi di rilevamento del flusso di lavoro viene fornito anche nel file Web.config denominato `Troubleshooting Tracking Profile`. Quando viene installato [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], un profilo predefinito con un nome vuoto viene configurato nel file Machine.config. Questo profilo viene usato dalla configurazione del comportamento di rilevamento ETW quando non viene specificato alcun nome di profilo né un nome di profilo vuoto.

 Il profilo di rilevamento del monitoraggio dell'integrità crea record di istanza del flusso di lavoro e record di propagazione degli errori di attività. Questo profilo viene creato aggiungendo il profilo di rilevamento seguente a un file di configurazione Web.config.

```xml
<<tracking>
      <profiles>
        <trackingProfile name="HealthMonitoring Tracking Profile">
          <workflow activityDefinitionId="*">
            <workflowInstanceQueries>
              <workflowInstanceQuery>
                <states>
                  <state name="Started"/>
                  <state name="Completed"/>
                  <state name="Aborted"/>
                  <state name="UnhandledException"/>
                </states>
            </workflowInstanceQuery>
           </workflowInstanceQueries>
            <faultPropagationQueries>
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>
            </faultPropagationQueries>
          </workflow>
        </trackingProfile>
       </profiles>
</tracking>
```

 Il profilo può essere modificato impostando la configurazione `EtwTrackingParticipant` sugli elementi seguenti.

```xml
<behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="HealthMonitoring Tracking Profile"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
```

#### <a name="to-clean-up-optional"></a>Per eseguire la pulizia (facoltativo)

1.  Aprire Visualizzatore eventi.

2.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **dell'applicazione Le applicazioni server**. Fare doppio clic su **analitico** e selezionare **Disattiva registro**.

3.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **dell'applicazione Le applicazioni server**. Fare doppio clic su **analitico** e selezionare **Cancella Log**.

4.  Scegliere il **cancellare** opzione per cancellare gli eventi.

## <a name="known-issue"></a>Problema noto

> [!NOTE]
>  Nel Visualizzatore eventi potrebbe non essere possibile decodificare gli eventi ETW. Si potrebbe visualizzare un messaggio di errore simile al seguente.
>
>  La descrizione per l'ID evento \<id > dall'origine Microsoft-Windows Server applicazioni-applicazioni nebyla nalezena. Il componente che ha generato l'evento non è installato nel computer locale oppure l'installazione è danneggiata. È possibile installare o ripristinare il componente nel computer locale.
>
>  Se si rileva questo errore, fare clic su Aggiorna nel riquadro Azioni. La decodifica dell'evento dovrebbe ora essere eseguita in modo corretto.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\EtwTracking`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://go.microsoft.com/fwlink/?LinkId=193959)
