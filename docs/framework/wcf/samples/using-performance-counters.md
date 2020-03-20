---
title: Utilizzo dei contatori delle prestazioni
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143577"
---
# <a name="using-performance-counters"></a>Utilizzo dei contatori delle prestazioni
In questo esempio viene illustrato come accedere ai contatori delle prestazioni di Windows Communication Foundation (WCF) e come creare contatori delle prestazioni definiti dall'utente. Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio, il client chiama i quattro metodi del servizio `ICalculator`. Questa procedura continua fino a quando il client viene interrotto dall'utente. Il servizio rimane inalterato.  
  
 I contatori delle prestazioni vengono abilitati nella sezione di diagnostica del file Web.config per il servizio, come illustrato nella configurazione di esempio seguente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 Questa attività può essere eseguita anche utilizzando lo strumento Editor di [configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Quando i contatori delle prestazioni sono abilitati, l'intera suite di contatori delle prestazioni WCF è abilitata per il servizio. .NET Framework gestisce automaticamente i dati relativi alle prestazioni a tre livelli: `ServiceModelService`, `ServiceModelEndpoint` e `ServiceModelOperation`. Per ognuno di questi livelli sono presenti dei contatori delle prestazioni, ad esempio "Chiamate", "Chiamate al secondo" e "Chiamate di sicurezza non autorizzate".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Per visualizzare i dati relativi alle prestazioni  
  
1. Avviare lo strumento Performance Monitor facendo `perfmon` clic su **Start**, **Esegui...**, immettere e scegliere **OK oppure** dal Pannello di controllo selezionare **Strumenti di amministrazione** e fare doppio clic su **Prestazioni**.  
  
    > [!NOTE]
    > Non è possibile aggiungere contatori mentre il codice di esempio è in esecuzione.  
  
2. Rimuovere i contatori delle prestazioni elencati selezionandoli e premendo CANC.  
  
3. Aggiungere contatori WCF facendo clic con il pulsante destro del mouse sul riquadro del grafico e scegliendo **Aggiungi contatori**. Nella finestra di dialogo **Aggiungi contatori** selezionare **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** nella casella di riepilogo a discesa Oggetto prestazioni. Selezionare i contatori che si desidera visualizzare nell'elenco.  
  
    > [!NOTE]
    > Non esistono contatori delle prestazioni WCF per un servizio se nel computer non sono presenti servizi WCF in esecuzione.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Per utilizzare l'editor di configurazione per abilitare i contatori  
  
1. Aprire un'istanza di SvcConfigEditor.exe.  
  
2. Scegliere **Apri** dal menu File, quindi fare clic su **File di configurazione...**.  
  
3. Passare alla cartella del servizio dell'applicazione di esempio e aprire il file Web.config.  
  
4. Fare clic su **Diagnostica** nell'albero di configurazione.  
  
5. Attivare/disattivare **il contatore delle prestazioni** nella finestra **Diagnostica** per visualizzare "Tutti".  
  
6. Salvare il file di configurazione e uscire dall'editor.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
