---
title: Traccia analitica WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 3ed9c5f08e89d978f8290dcda5ab1ecfd8b9c56c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094826"
---
# <a name="wcf-analytic-tracing"></a>Traccia analitica WCF
In questo esempio viene illustrato come aggiungere eventi di traccia nel flusso di tracce analitiche che Windows Communication Foundation (WCF) scrive in ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Le tracce analitiche hanno lo scopo di semplificare la visibilità all'interno dei servizi senza un'elevata riduzione delle prestazioni. In questo esempio viene illustrato come utilizzare le API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> per scrivere eventi che si integrano con i servizi WCF.  
  
 Per ulteriori informazioni sulle API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>, vedere <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Per ulteriori informazioni sulla traccia eventi in Windows, vedere [migliorare il debug e l'ottimizzazione delle prestazioni con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).  
  
## <a name="disposing-eventprovider"></a>Eliminazione di EventProvider  
 In questo esempio viene utilizzata la classe <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, che implementa <xref:System.IDisposable?displayProperty=nameWithType>. Quando si implementa la traccia per un servizio WCF, è probabile che sia possibile utilizzare le risorse del <xref:System.Diagnostics.Eventing.EventProvider>per la durata del servizio. Per tale motivo e per ragioni di leggibilità, in questo esempio l'oggetto <xref:System.Diagnostics.Eventing.EventProvider> con wrapper non viene mai eliminato. Se per qualche motivo il servizio ha requisiti diversi per la traccia ed è necessario eliminare tale risorsa, occorre modificare l'esempio in base alle procedure consigliate per l'eliminazione di risorse non gestite. Per ulteriori informazioni sull'eliminazione di risorse non gestite, vedere [implementazione di un metodo Dispose](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).  
  
## <a name="self-hosting-vs-web-hosting"></a>Differenze tra self-hosting e hosting Web  
 Per i servizi ospitati sul Web, le tracce analitiche di WCF forniscono un campo denominato "HostReference", che viene utilizzato per identificare il servizio che emette le tracce. Le tracce utente estensibili possono far parte di tale modello e in questo esempio vengono descritte le procedure consigliate per effettuare tale operazione. Il formato di un riferimento all'host Web quando il carattere&#124;della pipe '' è effettivamente visualizzato nella stringa risultante può essere uno dei seguenti:  
  
- Se l'applicazione non è alla radice.  
  
     \<SiteName >\<ApplicationVirtualPath&#124; >\<ServiceVirtualPath&#124; >\<ServiceName >  
  
- Se l'applicazione è alla radice.  
  
     \<SiteName&#124; >\<ServiceVirtualPath&#124; >\<ServiceName >  
  
 Per i servizi indipendenti, le tracce analitiche di WCF non popolano il campo "HostReference". La classe `WCFUserEventProvider` in questo esempio si comporta coerentemente quando viene utilizzata da un servizio indipendente.  
  
## <a name="custom-event-details"></a>Informazioni dettagliate su eventi personalizzati  
 Il manifesto del provider di eventi ETW di WCF definisce tre eventi progettati per essere creati dagli autori del servizio WCF dall'interno del codice del servizio. Nella tabella riportata di seguito viene illustrata una suddivisione dei tre eventi.  
  
|Event|Descrizione|ID evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Generare questo evento quando nel servizio si verifica un evento degno di nota che non è tuttavia un problema. Ad esempio, è possibile generare un evento dopo avere effettuato correttamente una chiamata a un database.|301|  
|UserDefinedWarningOccurred|Generare questo evento quando si verifica un problema che potrebbe comportare un errore in futuro. Ad esempio, è possibile generare un evento di avviso quando una chiamata a un database non riesce ma è comunque possibile recuperarla eseguendo il fallback a un archivio dati ridondante.|302|  
|UserDefinedErrorOccurred|Generare questo evento quando il comportamento del servizio non è quello previsto. Ad esempio, è possibile generare un evento se una chiamata a un database non riesce e non è possibile recuperare i dati altrove.|303|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1. Con Visual Studio 2012 aprire il file della soluzione WCFAnalyticTracingExtensibility. sln.  
  
2. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3. Per eseguire la soluzione, premere CTRL+F5.  
  
     Nella Web browser fare clic su **Calculator. svc**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.  
  
4. Eseguire il client di prova WCF (WcfTestClient. exe).  
  
     Il client di prova WCF (WcfTestClient. exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. La directory di installazione predefinita di Visual Studio 2012 è `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. Nel client di prova WCF aggiungere il servizio selezionando **file**e quindi **Aggiungi servizio**.  
  
     Aggiungere l'indirizzo dell'endpoint nella casella di input.  
  
6. Fare clic su **OK** per chiudere la finestra di dialogo.  
  
     Il servizio ICalculator viene aggiunto nel riquadro sinistro in **progetti di servizio**.  
  
7. Aprire l'applicazione Visualizzatore eventi.  
  
     Prima di richiamare il servizio, avviare Visualizzatore eventi e verificare che il registro eventi sia in ascolto di eventi di rilevamento generati dal servizio WCF.  
  
8. Dal menu **Start** , selezionare **strumenti di amministrazione**, quindi **Visualizzatore eventi**. Abilitare i log **analitici** e di **debug** .  
  
9. Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **server applicazioni-applicazioni**. Fare clic con il pulsante destro del mouse su **server applicazioni-applicazioni**, selezionare **Visualizza**, quindi **Visualizza registri analitici e di debug**.  
  
     Verificare che l'opzione **Mostra log analitici e di debug** sia selezionata. Abilitare il registro **analitico** .  
  
     Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, server applicazioni **-applicazioni**, quindi **analitico**. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Abilita log**.  
  
10. Testare il servizio usando il client di prova WCF.  
  
    1. Nel client di prova WCF fare doppio clic su **Aggiungi ()** nel nodo del servizio ICalculator.  
  
         Il metodo **Add ()** viene visualizzato nel riquadro destro con due parametri.  
  
    2. Digitare 2 per il primo parametro e 3 per il secondo parametro.  
  
    3. Fare clic su **richiama** per richiamare il metodo.  
  
11. Passare alla finestra **Visualizzatore eventi** che è già stata aperta. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **server applicazioni-applicazioni**.  
  
12. Fare clic con il pulsante destro del mouse sul nodo **analitico** e selezionare **Aggiorna**.  
  
     Gli eventi vengono visualizzati nel riquadro destro.  
  
13. Individuare l'evento con l'ID 303 e fare doppio clic per aprirlo e verificarne il contenuto.  
  
     Questo evento è stato generato dal metodo `Add()` del servizio ICalculator e ha un payload uguale a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1. Aprire il **Visualizzatore eventi**.  
  
2. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **Application-Server-** Applications. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Disattiva log**.  
  
3. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Application-Server-Applications**, quindi **analitico**. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Cancella log**.  
  
4. Fare clic su **Cancella** per cancellare gli eventi.  
  
## <a name="known-issue"></a>Problemi noti  
 Si è verificato un problema noto nel **Visualizzatore eventi** in cui potrebbe non riuscire a decodificare gli eventi ETW. Potrebbe essere visualizzato un messaggio di errore che indica che la descrizione dell'ID evento \<ID > dall'origine Microsoft-Windows-Server applicazioni-applicazioni non è stata trovata. Il componente che genera questo evento non è installato nel computer locale o l'installazione è danneggiata. È possibile installare o ripristinare il componente nel computer locale. " Se si verifica questo errore, selezionare **Aggiorna** dal menu **azioni** . L'evento dovrebbe procedere alla decodifica in modo corretto.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
