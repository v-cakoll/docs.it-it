---
title: Attivazione basata sulla configurazione
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: e016dffdaf93b222c1fd2380bfa175256b009068
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742316"
---
# <a name="configuration-based-activation"></a>Attivazione basata sulla configurazione
Questo esempio viene illustrato come attivare servizi Windows Communication Foundation (WCF) senza richiedere un file con estensione svc.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio, il client è il client di prova WCF e il servizio è ospitato in IIS.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>Attivazione di servizi senza richiedere un file con estensione svc  
 In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], per l'attivazione di un servizio è richiesto un file con estensione svc. Ciò causa un ulteriore sovraccarico di gestione, perché insieme all'applicazione, è necessario distribuire e gestire un file aggiuntivo. Con la versione di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], è possibile configurare i componenti di attivazione utilizzando il file di configurazione dell'applicazione.  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] introduce un nuovo elemento di configurazione (<xref:System.ServiceModel.Configuration.ServiceActivationElement>) nella sezione <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> del file di configurazione dell'applicazione. La raccolta <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> accetta una raccolta di servizi da attivare, come mostrato nell'esempio di codice seguente.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 È importante notare che la configurazione ha un aspetto molto simile alla configurazione di file con estensione svc. Un attributo aggiuntivo introdotto è `relativeAddress`, che fornisce l'indirizzo del servizio. L'indirizzo relativo è anche il percorso virtuale per il servizio. L'host recupera il file Web.config del file dal percorso `virtualPath`, se presente; in caso contrario, l'host esegue ricerche in modo ricorsivo nella cartella padre.  
  
> [!NOTE]
>  Per il funzionamento di questo esempio, è necessario l'hosting in IIS.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire il file Service.csproj.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Eseguire il test del servizio eseguendo WCFTestClient.exe.  
  
4.  Utilizzando [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], passare alla cartella %SystemDrive%\Programmi\Microsoft Visual Studio 10.0\Common7\IDE.  
  
5.  Eseguire WcfTestClient.exe.  
  
6.  Impostare l'indirizzo MEX del servizio.  
  
7.  Premere CTRL+SHIFT+A per impostare l'indirizzo del servizio.  
  
8.  Impostare l'indirizzo http://localhost/ServiceModelSamples/Calculator.svc.  
  
9. Eseguire l'operazione `Add`. Impostare il valore nel parametro `n1` su 10 e il valore nel parametro `n2` su 15.  
  
10. Premere **richiamare**.  
  
     Il risultato previsto è 25.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Una volta compilata la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in IIS. La directory ServiceModelSamples deve essere visualizzata come applicazione IIS.  
  
4.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)
