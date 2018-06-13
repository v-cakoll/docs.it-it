---
title: Estrarre dati di WF utilizzando il rilevamento
ms.date: 03/30/2017
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
ms.openlocfilehash: 22b147521d4ce0c72fadfb7adc81e05f10ce52b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519873"
---
# <a name="extract-wf-data-using-tracking"></a>Estrarre dati di WF utilizzando il rilevamento
In questo esempio viene illustrato come usare il rilevamento del flusso di lavoro per estrarre variabili e argomenti del flusso di lavoro dalle attività. Vengono inoltre illustrate l'aggiunta di annotazioni ai record di rilevamento e l'estrazione del payload di dati all'interno dei record di rilevamento personalizzati. Nell'esempio viene usato il partecipante del rilevamento Traccia eventi per Windows (ETW) per estrarre i dati dal flusso di lavoro.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Windows Workflow Foundation (WF) fornisce il rilevamento per ottenere visibilità nell'esecuzione di un'istanza del flusso di lavoro. Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo. Insieme ai record di rilevamento del flusso di lavoro, da quest'ultimo è possibile estrarre i dati presenti nell'istanza del flusso di lavoro. Nell'elenco seguente sono indicati in dettaglio i tipi di dati che possono essere estratti dai record di rilevamento:  
  
1.  Variabili del flusso di lavoro all'interno di un'attività e record di rilevamento durante l'esecuzione dell'attività.  
  
     Le variabili del flusso di lavoro da estrarre sono specificate in un profilo. Le variabili da estrarre possono essere specificate solo con `ActivityStateQueries`. Nell'esempio di codice seguente viene illustrato un profilo di rilevamento usato per estrarre la variabile del flusso di lavoro da un'attività.  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  Argomenti e record di rilevamento dello stato dell'attività.  
  
     Gli argomenti definiscono il modo in cui i dati entrano ed escono da un'attività. Gli argomenti da estrarre vengono specificati usando un oggetto <xref:System.Activities.Tracking.ActivityStateQuery>. L'esempio di codice seguente è un profilo di rilevamento che estrae l'argomento `Value`.  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  Le annotazioni sono coppie chiave/valore che possono essere aggiunte a qualsiasi record di rilevamento creato.  
  
     Le annotazioni servono come meccanismo di tag per i record di rilevamento, vengono aggiunte ai record di rilevamento tramite un profilo di rilevamento e possono essere aggiunte a qualsiasi tipo di query di rilevamento di un flusso di lavoro. L'esempio di codice seguente è un profilo di rilevamento che mostra il modo in cui è possibile aggiungere un'annotazione a un record di rilevamento.  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  I record di rilevamento personalizzati vengono creati dalle attività definite dall'utente.  
  
     I record di rilevamento personalizzati possono contenere i dati di payload definiti all'interno di questa attività. La sottoscrizione di record di rilevamento personalizzati in un profilo di rilevamento consente l'estrazione del payload all'interno del record di rilevamento. I record di rilevamento personalizzati possono essere estratti con un oggetto <xref:System.Activities.Tracking.TrackingQuery> personalizzato. L'esempio di codice seguente è un profilo di rilevamento che estrae un record di rilevamento personalizzato insieme al payload.  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 Nell'esempio vengono illustrate l'estrazione di variabili, argomenti, record personalizzati e l'aggiunta di annotazioni tramite un profilo specificato in un file Web.config. Il rilevamento è abilitato sul servizio flusso di lavoro di esempio aggiungendo un elemento del comportamento `<etwTracking>`. Nell'esempio di codice seguente viene abilitato il rilevamento per il profilo di rilevamento `ExtractWorkflowVariables`.  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WFStockPriceApplication.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere F5.  
  
     Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.  
  
4.  Nel browser fare clic su StockPriceService.xamlx.  
  
5.  Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale. Copiare questo indirizzo.  
  
     Nell'esempio seguente viene mostrato un indirizzo WSDL del servizio locale. `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  Prima di richiamare il servizio, avviare Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per rilevare eventi creati dal servizio del flusso di lavoro.  
  
7.  Dal **avviare** dal menu **strumenti di amministrazione** e quindi **Visualizzatore eventi**.  
  
8.  Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, e **Microsoft**. Fare doppio clic su **Microsoft** e selezionare **vista** e quindi **Visualizza registri analitici e Debug**.  
  
     Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata.  
  
9. Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Attiva registro**.  
  
10. Usando [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], aprire il client di WCF.  
  
     Client di prova WCF (WcfTestClient.exe) si trova nella \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] cartella di installazione > \Common7\IDE\ cartella.  
  
     La cartella di installazione di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] predefinita è C:\Programmi\Microsoft Visual Studio 10.0.  
  
11. Nel client di prova WCF selezionare **Aggiungi servizio** dal **File** menu.  
  
     Aggiungere l'indirizzo WSDL del servizio locale che è stato copiato precedentemente nella casella di input.  
  
12. Nel client di prova WCF fare doppio clic su `GetStockPrice`.  
  
     Verrà visualizzato il metodo `GetStockPrice`. La richiesta accetta un parametro. Utilizzare il valore **Contoso**.  
  
13. Fare clic su **richiamare**.  
  
14. Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **aggiornamento**. Gli ID degli eventi flusso di lavoro sono compresi tra 100 e 199.  
  
     Gli eventi contengono annotazioni, variabili, argomenti e record di rilevamento personalizzati che possono essere visualizzati nel visualizzatore eventi.  
  
## <a name="cleaning-up-in-the-event-viewer"></a>Pulizia nel Visualizzatore eventi  
 Il canale analitico nel registro eventi può essere pulito nel Visualizzatore eventi eseguendo le operazioni seguenti.  
  
#### <a name="to-clean-up-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1.  Aprire Visualizzatore eventi.  
  
2.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **applicazione Applicazioni server**. Fare doppio clic su **analitico** e selezionare **Disattiva registro**.  
  
3.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **applicazione Applicazioni server**. Fare doppio clic su **analitico** e selezionare **Cancella Log**.  
  
     Scegliere il **deselezionare** opzione per cancellare gli eventi.  
  
## <a name="known-issue"></a>Problema noto  
  
> [!NOTE]
>  Nel Visualizzatore eventi potrebbe non essere possibile decodificare gli eventi ETW. Si potrebbe visualizzare un messaggio di errore simile al seguente.  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  Se si verifica questo errore, fare clic su **aggiornamento** nel riquadro azioni. La decodifica dell'evento dovrebbe ora essere eseguita in modo corretto.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di monitoraggio di AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
