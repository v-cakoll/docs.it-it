---
title: Traccia analitica WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 9ed89bdbe2469a96f2a959c9fda8442e80b6f7ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723355"
---
# <a name="wcf-analytic-tracing"></a>Traccia analitica WCF
Questo esempio viene illustrato come aggiungere eventi di traccia nel flusso di tracce analitiche che Windows Communication Foundation (WCF) scrive in ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Le tracce analitiche hanno lo scopo di semplificare la visibilità all'interno dei servizi senza un'elevata riduzione delle prestazioni. In questo esempio viene illustrato come utilizzare il <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API per scrivere eventi che si integrano con i servizi WCF.  
  
 Per altre informazioni sul <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API, vedere <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Per altre informazioni sulla traccia di eventi in Windows, vedere [migliora il debug e ottimizzazione delle prestazioni con ETW](https://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Eliminazione di EventProvider  
 In questo esempio viene utilizzata la classe <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, che implementa <xref:System.IDisposable?displayProperty=nameWithType>. Quando si implementa la traccia per un servizio WCF, è probabile che è possibile utilizzare il <xref:System.Diagnostics.Eventing.EventProvider>di risorse per la durata del servizio. Per tale motivo e per ragioni di leggibilità, in questo esempio l'oggetto <xref:System.Diagnostics.Eventing.EventProvider> con wrapper non viene mai eliminato. Se per qualche motivo il servizio ha requisiti diversi per la traccia ed è necessario eliminare tale risorsa, occorre modificare l'esempio in base alle procedure consigliate per l'eliminazione di risorse non gestite. Per altre informazioni sull'eliminazione delle risorse non gestite, vedere [implementazione di un metodo Dispose](https://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Differenze tra self-hosting e hosting Web  
 Per i servizi ospitati su Web, le tracce analitiche di WCF forniscono un campo, denominato "HostReference", che consente di identificare il servizio che sta generando le tracce. Le tracce utente estensibili possono far parte di tale modello e in questo esempio vengono descritte le procedure consigliate per effettuare tale operazione. Il formato di un host Web di riferimento quando la pipe '&#124;' caratteri viene effettivamente visualizzato nella finestra di stringa può essere una qualsiasi delle operazioni seguenti:  
  
- Se l'applicazione non è alla radice.  
  
     \<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
- Se l'applicazione è alla radice.  
  
     \<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
 Per i servizi self-hosted, le tracce analitiche di WCF non popolano il campo "HostReference". La classe `WCFUserEventProvider` in questo esempio si comporta coerentemente quando viene utilizzata da un servizio indipendente.  
  
## <a name="custom-event-details"></a>Informazioni dettagliate su eventi personalizzati  
 Manifesto del Provider di eventi ETW di WCF definisce tre eventi progettati per essere generati dagli autori del servizio WCF all'interno di codice del servizio. Nella tabella riportata di seguito viene illustrata una suddivisione dei tre eventi.  
  
|event|Descrizione|ID evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Generare questo evento quando nel servizio si verifica un evento degno di nota che non è tuttavia un problema. Ad esempio, è possibile generare un evento dopo avere effettuato correttamente una chiamata a un database.|301|  
|UserDefinedWarningOccurred|Generare questo evento quando si verifica un problema che potrebbe comportare un errore in futuro. Ad esempio, è possibile generare un evento di avviso quando una chiamata a un database non riesce ma è comunque possibile recuperarla eseguendo il fallback a un archivio dati ridondante.|302|  
|UserDefinedErrorOccurred|Generare questo evento quando il comportamento del servizio non è quello previsto. Ad esempio, è possibile generare un evento se una chiamata a un database non riesce e non è possibile recuperare i dati altrove.|303|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1. Usa Visual Studio 2012, aprire il file della soluzione Wcfanalytictracingextensibility.  
  
2. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3. Per eseguire la soluzione, premere CTRL+F5.  
  
     Nel Web browser, fare clic su **Calculator**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.  
  
4. Eseguire il client di prova WCF (WcfTestClient.exe).  
  
     Il client di prova WCF (WcfTestClient.exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. La directory di installazione di Visual Studio 2012 impostazione predefinita è `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. All'interno del client di test WCF, aggiungere il servizio selezionando **File**e quindi **Aggiungi servizio**.  
  
     Aggiungere l'indirizzo dell'endpoint nella casella di input.  
  
6. Fare clic su **OK** per chiudere la finestra di dialogo.  
  
     Il servizio ICalculator viene aggiunto nel riquadro sinistro sotto **progetti di servizi**.  
  
7. Aprire l'applicazione Visualizzatore eventi.  
  
     Prima di richiamare il servizio, avviare Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per rilevare eventi creati dal servizio WCF.  
  
8. Dal **avviare** dal menu **strumenti di amministrazione**e quindi **Visualizzatore eventi**. Abilitare la **analitico** e **Debug** i log.  
  
9. Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**. Fare doppio clic su **Server applicazioni-applicazioni**, selezionare **View**e quindi **Visualizza registri analitici e Debug**.  
  
     Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata. Abilitare la **analitico** log.  
  
     Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**e quindi **analitiche**. Fare doppio clic su **analitico** e selezionare **Attiva registro**.  
  
10. Testare il servizio usando il client di prova WCF.  
  
    1. Nel Client di prova WCF fare doppio clic **Add ()** nel nodo del servizio ICalculator.  
  
         Il **Add ()** metodo viene visualizzato nel riquadro di destra con due parametri.  
  
    2. Digitare 2 per il primo parametro e 3 per il secondo parametro.  
  
    3. Fare clic su **Invoke** per richiamare il metodo.  
  
11. Andare alla **Visualizzatore eventi** finestra che è già aperta. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **dell'applicazione Le applicazioni server**.  
  
12. Fare doppio clic il **analitico** nodo e selezionare **aggiornare**.  
  
     Gli eventi vengono visualizzati nel riquadro destro.  
  
13. Individuare l'evento con l'ID 303 e fare doppio clic per aprirlo e verificarne il contenuto.  
  
     Questo evento viene generato dal `Add()` metodo del servizio ICalculator e ha un payload uguale a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1. Aprire **Visualizzatore eventi**.  
  
2. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Disattiva registro**.  
  
3. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**e quindi **analitiche**. Fare doppio clic su **analitico** e selezionare **Cancella Log**.  
  
4. Fare clic su **cancellare** per cancellare gli eventi.  
  
## <a name="known-issue"></a>Problema noto  
 È un problema noto durante il **Visualizzatore eventi** potrebbe non essere possibile decodificare gli eventi ETW. Viene visualizzato un messaggio di errore con la dicitura: "La descrizione per l'ID evento \<id > dall'origine Microsoft-Windows Server applicazioni-applicazioni nebyla nalezena. Il componente che ha generato l'evento non è installato nel computer locale oppure l'installazione è danneggiata. È possibile installare o ripristinare il componente nel computer locale." Se si verifica questo errore, selezionare **Refresh** dalle **azioni** menu. L'evento dovrebbe procedere alla decodifica in modo corretto.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
