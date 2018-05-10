---
title: Utilizzo dei contatori delle prestazioni
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 8784b4a481b8313d370aad1d8f265dcb44ab3ed6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="using-performance-counters"></a>Utilizzo dei contatori delle prestazioni
Questo esempio viene illustrato come accedere ai contatori delle prestazioni di Windows Communication Foundation (WCF) e su come creare contatori delle prestazioni definiti dall'utente. Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio, il client chiama i quattro metodi del servizio `ICalculator`. Questa procedura continua fino a quando il client viene interrotto dall'utente. Il servizio rimane inalterato.  
  
 I contatori delle prestazioni vengono abilitati nella sezione di diagnostica del file Web.config per il servizio, come illustrato nella configurazione di esempio seguente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Questa attività può essere eseguita anche utilizzando la [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Quando sono abilitati i contatori delle prestazioni, l'intera suite di contatori delle prestazioni WCF è abilitata per il servizio. .NET Framework gestisce automaticamente i dati relativi alle prestazioni a tre livelli: `ServiceModelService`, `ServiceModelEndpoint` e `ServiceModelOperation`. Per ognuno di questi livelli sono presenti dei contatori delle prestazioni, ad esempio "Chiamate", "Chiamate al secondo" e "Chiamate di sicurezza non autorizzate".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Per visualizzare i dati relativi alle prestazioni  
  
1.  Avviare lo strumento Performance Monitor facendo **avviare**, **Esegui...** , immettere `perfmon` e fare clic su **OK,** oppure dal Pannello di controllo, selezionare **strumenti di amministrazione** fare doppio clic su **prestazioni**.  
  
    > [!NOTE]
    >  Non è possibile aggiungere contatori mentre il codice di esempio è in esecuzione.  
  
2.  Rimuovere i contatori delle prestazioni elencati selezionandoli e premendo CANC.  
  
3.  Aggiungere contatori WCF il pulsante destro del riquadro del grafico e scegliendo **Aggiungi contatori**. Nel **Aggiungi contatori** nella finestra di dialogo **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** nell'oggetto prestazione casella a discesa. Selezionare i contatori che si desidera visualizzare nell'elenco.  
  
    > [!NOTE]
    >  Non sono presenti contatori di prestazioni WCF per un servizio se non sono servizi WCF in esecuzione nel computer.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Per utilizzare l'editor di configurazione per abilitare i contatori  
  
1.  Aprire un'istanza di SvcConfigEditor.exe.  
  
2.  Dal menu File, fare clic su **aprire** e quindi fare clic su **file di configurazione...** .  
  
3.  Passare alla cartella del servizio dell'applicazione di esempio e aprire il file Web.config.  
  
4.  Fare clic su **diagnostica** nell'albero configurazione.  
  
5.  Attiva/disattiva **contatore delle prestazioni** nel **diagnostica** finestra per visualizzare "All".  
  
6.  Salvare il file di configurazione e uscire dall'editor.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di monitoraggio di AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
