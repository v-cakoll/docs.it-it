---
title: Utilizzo dei contatori delle prestazioni
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 0b63cdc145ff8806c26b255500bcb2a132e9ef9f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596500"
---
# <a name="using-performance-counters"></a>Utilizzo dei contatori delle prestazioni
In questo esempio viene illustrato come accedere ai contatori delle prestazioni Windows Communication Foundation (WCF) e come creare contatori delle prestazioni definiti dall'utente. Questo esempio è basato sul [Introduzione](getting-started-sample.md).  
  
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
  
 Questa attività può essere eseguita anche tramite lo [strumento Editor di configurazione (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Quando i contatori delle prestazioni sono abilitati, l'intero gruppo di contatori delle prestazioni WCF è abilitato per il servizio. .NET Framework gestisce automaticamente i dati relativi alle prestazioni a tre livelli: `ServiceModelService`, `ServiceModelEndpoint` e `ServiceModelOperation`. Per ognuno di questi livelli sono presenti dei contatori delle prestazioni, ad esempio "Chiamate", "Chiamate al secondo" e "Chiamate di sicurezza non autorizzate".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Per visualizzare i dati relativi alle prestazioni  
  
1. Avviare lo strumento Performance Monitor facendo clic sul pulsante **Start**, scegliere **Esegui...**, immettere `perfmon` e fare clic su **OK** oppure nel pannello di controllo selezionare **strumenti di amministrazione** e fare doppio clic su **prestazioni**.  
  
    > [!NOTE]
    > Non è possibile aggiungere contatori mentre il codice di esempio è in esecuzione.  
  
2. Rimuovere i contatori delle prestazioni elencati selezionandoli e premendo CANC.  
  
3. Per aggiungere i contatori WCF, fare clic con il pulsante destro del mouse sul riquadro grafico e scegliere **Aggiungi contatori**. Nella finestra di dialogo **Aggiungi contatori** selezionare **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** nella casella di riepilogo a discesa oggetto prestazione. Selezionare i contatori che si desidera visualizzare nell'elenco.  
  
    > [!NOTE]
    > Non sono disponibili contatori delle prestazioni WCF per un servizio se non sono in esecuzione servizi WCF nel computer.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Per utilizzare l'editor di configurazione per abilitare i contatori  
  
1. Aprire un'istanza di SvcConfigEditor.exe.  
  
2. Scegliere **Apri** dal menu file e quindi fare clic su **file di configurazione...**.  
  
3. Passare alla cartella del servizio dell'applicazione di esempio e aprire il file Web.config.  
  
4. Fare clic su **diagnostica** nella struttura di configurazione.  
  
5. Consente di impostare il **contatore delle prestazioni** nella finestra di **diagnostica** per visualizzare ' all'.  
  
6. Salvare il file di configurazione e uscire dall'editor.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
