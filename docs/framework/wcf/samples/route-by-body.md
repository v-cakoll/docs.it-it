---
title: Routing in base al corpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: b8a3f7785d7d59d8ad85d6dddde7fd6a04a12d63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320717"
---
# <a name="route-by-body"></a>Routing in base al corpo
In questo esempio viene illustrato come implementare un servizio che accetta oggetti di messaggi con qualsiasi azione SOAP. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice. Il servizio implementa una sola operazione `Calculate` che accetta un parametro di richiesta <xref:System.ServiceModel.Channels.Message> e restituisce una risposta <xref:System.ServiceModel.Channels.Message>.  
  
 In questo esempio il client è un'applicazione console (con estensione exe) e il servizio è ospitato in IIS.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene illustrata la distribuzione dei messaggi in base al contenuto del corpo. Il meccanismo di invio messaggio predefinite del modello del servizio Windows Communication Foundation (WCF) si basa sulle azioni del messaggio. Tuttavia, molti servizi Web esistenti definiscono tutte le relative operazioni con Action="". È impossibile compilare un servizio basato su WSDL che continua a distribuire messaggi di richiesta in base alle informazioni dell'azione. In questo esempio viene mostrato un contratto di servizio basato su WSDL (WSDL è contenuto nel file Service.wsdl incluso con l'esempio). Il contratto di servizio è Calcolatrice, simile a quella usata nel [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md). Tuttavia `[OperationContract]` specifica `Action=""` per tutte le operazioni.  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 Se dispone di un contratto, un servizio richiede un comportamento di distribuzione `DispatchByBodyBehavior` personalizzato per consentire la distribuzione dei messaggi tra le operazioni. Questo comportamento di distribuzione Inizializza il `DispatchByBodyElementOperationSelector` selettore dell'operazione personalizzato con una tabella dei nomi delle operazioni con chiave basata sul QName dei rispettivi elementi wrapper. `DispatchByBodyElementOperationSelector` analizza il tag iniziale del primo elemento figlio del corpo e seleziona l'operazione utilizzando la tabella menzionata.  
  
 Il client usa un proxy generato automaticamente dal WSDL, esportato usando il servizio [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 Se le azioni di tutte le operazioni sono vuote non si verifica alcun impatto sul codice client, eccetto che per i parametri Action nel proxy generato automaticamente.  
  
 Il codice client esegue molti calcoli. Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
