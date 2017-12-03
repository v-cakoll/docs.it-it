---
title: Traccia analitica WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c238d4c923b00a6c3387caa9bdafd69b126753c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-analytic-tracing"></a>Traccia analitica WCF
In questo esempio viene descritto come aggiungere eventi di traccia nel flusso di tracce analitiche scritte da [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Le tracce analitiche hanno lo scopo di semplificare la visibilità all'interno dei servizi senza un'elevata riduzione delle prestazioni. Questo esempio mostra come utilizzare le API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> per scrivere eventi che si integrano con i servizi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>, vedere <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Per ulteriori informazioni sulla traccia degli eventi di Windows, vedere [migliora il debug e ottimizzazione delle prestazioni con ETW](http://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Eliminazione di EventProvider  
 In questo esempio viene utilizzata la classe <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, che implementa <xref:System.IDisposable?displayProperty=nameWithType>. Quando si implementa la traccia per un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è possibile utilizzare le risorse di <xref:System.Diagnostics.Eventing.EventProvider> per la durata del servizio. Per tale motivo e per ragioni di leggibilità, in questo esempio l'oggetto <xref:System.Diagnostics.Eventing.EventProvider> con wrapper non viene mai eliminato. Se per qualche motivo il servizio ha requisiti diversi per la traccia ed è necessario eliminare tale risorsa, occorre modificare l'esempio in base alle procedure consigliate per l'eliminazione di risorse non gestite. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]eliminazione di risorse non gestite, vedere [implementazione di un metodo Dispose](http://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Differenze tra self-hosting e hosting Web  
 Per i servizi ospitati su Web, le tracce analitiche di WCF forniscono un campo, denominato "HostReference", viene utilizzato per identificare il servizio che sta generando le tracce. Le tracce utente estensibili possono far parte di tale modello e in questo esempio vengono descritte le procedure consigliate per effettuare tale operazione. Il formato di un host Web riferimento quando la pipe ' &#124;' carattere viene visualizzato nella finestra di stringa può essere uno dei seguenti:  
  
-   Se l'applicazione non è alla radice.  
  
     \<Nome sito >\<ApplicationVirtualPath > &#124;\< ServiceVirtualPath > &#124; \<ServiceName >  
  
-   Se l'applicazione è alla radice.  
  
     \<Nome sito > &#124; \<ServiceVirtualPath > &#124; \<ServiceName >  
  
 Per i servizi indipendenti, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]di tracce analitiche non popolano il campo "HostReference". La classe `WCFUserEventProvider` in questo esempio si comporta coerentemente quando viene utilizzata da un servizio indipendente.  
  
## <a name="custom-event-details"></a>Informazioni dettagliate su eventi personalizzati  
 Il manifesto del provider di eventi ETW di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definisce tre eventi progettati per essere generati dagli autori del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dall'interno del codice del servizio. Nella tabella riportata di seguito viene illustrata una suddivisione dei tre eventi.  
  
|Evento|Descrizione|ID evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Generare questo evento quando nel servizio si verifica un evento degno di nota che non è tuttavia un problema. Ad esempio, è possibile generare un evento dopo avere effettuato correttamente una chiamata a un database.|301|  
|UserDefinedWarningOccurred|Generare questo evento quando si verifica un problema che potrebbe comportare un errore in futuro. Ad esempio, è possibile generare un evento di avviso quando una chiamata a un database non riesce ma è comunque possibile recuperarla eseguendo il fallback a un archivio dati ridondante.|302|  
|UserDefinedErrorOccurred|Generare questo evento quando il comportamento del servizio non è quello previsto. Ad esempio, è possibile generare un evento se una chiamata a un database non riesce e non è possibile recuperare i dati altrove.|303|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire il file della soluzione WCFAnalyticTracingExtensibility.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
     Nel Web browser, fare clic su **Calculator.svc**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.  
  
4.  Eseguire il client di prova [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).  
  
     Il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client di prova (WcfTestClient.exe) si trova nella \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directory di installazione > \Common7\IDE\ WcfTestClient.exe (impostazione predefinita [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] è c:\Programmi\Microsoft Visual Studio 10.0).  
  
5.  All'interno di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client di prova, aggiungere il servizio selezionando **File**e quindi **Aggiungi servizio**.  
  
     Aggiungere l'indirizzo dell'endpoint nella casella di input.  
  
6.  Fare clic su **OK** per chiudere la finestra di dialogo.  
  
     Il servizio ICalculator viene aggiunto nel riquadro sinistro sotto **progetti di servizi**.  
  
7.  Aprire l'applicazione Visualizzatore eventi.  
  
     Prima di richiamare il servizio, avviare Visualizzatore eventi e verificare che il registro eventi sia in ascolto per rilevare gli eventi generati dal servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
8.  Dal **avviare** dal menu **strumenti di amministrazione**e quindi **Visualizzatore eventi**. Abilitare il **analitico** e **Debug** log.  
  
9. Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**. Fare doppio clic su **Server applicazioni-applicazioni**selezionare **vista**e quindi **Visualizza registri analitici e Debug**.  
  
     Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata. Abilitare il **analitico** log.  
  
     Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**e quindi **analitiche**. Fare doppio clic su **analitico** e selezionare **Attiva registro**.  
  
10. Testare il servizio usando il client di prova WCF.  
  
    1.  Nel Client di prova WCF fare doppio clic su **Add** nel nodo del servizio ICalculator.  
  
         Il **Add** metodo verrà visualizzato nel riquadro a destra con due parametri.  
  
    2.  Digitare 2 per il primo parametro e 3 per il secondo parametro.  
  
    3.  Fare clic su **Invoke** per richiamare il metodo.  
  
11. Passare al **Visualizzatore eventi** finestra già aperta. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **applicazione Applicazioni server**.  
  
12. Fare doppio clic su di **analitico** nodo e selezionare **aggiornamento**.  
  
     Gli eventi vengono visualizzati nel riquadro destro.  
  
13. Individuare l'evento con l'ID 303 e fare doppio clic per aprirlo e verificarne il contenuto.  
  
     Questo evento viene generato dal `Add()` metodo del servizio ICalculator e ha un payload uguale a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1.  Aprire **Visualizzatore eventi**.  
  
2.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Disattiva registro**.  
  
3.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**e quindi **analitiche**. Fare doppio clic su **analitico** e selezionare **Cancella Log**.  
  
4.  Fare clic su **deselezionare** per cancellare gli eventi.  
  
## <a name="known-issue"></a>Problema noto  
 Si verifica un problema noto nel **Visualizzatore eventi** in cui potrebbe non riuscire a decodificare eventi ETW. Si può vedere un messaggio di errore: "la descrizione per l'ID evento \<id > dall'origine Microsoft-Windows-Application Server applicazioni non è state trovate. Il componente che ha generato l'evento non è installato nel computer locale oppure l'installazione è danneggiata. È possibile installare o ripristinare il componente nel computer locale." Se si verifica questo errore, selezionare **aggiornamento** dal **azioni** menu. L'evento dovrebbe procedere alla decodifica in modo corretto.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di monitoraggio di AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
