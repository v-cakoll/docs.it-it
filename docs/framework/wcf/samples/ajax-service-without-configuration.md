---
title: Servizio AJAX senza configurazione
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 60b61a26574764f0f2ea4ca834c5ba92b49a043d
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845047"
---
# <a name="ajax-service-without-configuration"></a>Servizio AJAX senza configurazione
Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio base di ASP.NET Asynchronous JavaScript and XML (AJAX) (un servizio che è possibile accedere usando codice JavaScript da un client browser Web) senza utilizzare alcuna configurazione Impostazioni. Il servizio usa sintassi speciale nel file con estensione svc per abilitare automaticamente un endpoint AJAX.  
  
 Supporto AJAX in WCF è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il `ScriptManager` controllo. Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi Ajax](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene usato il servizio AJAX con il protocollo HTTP POST. Come descritto nel [base del servizio AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> viene usato per ospitare il servizio.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aggiunge automaticamente un elemento <xref:System.ServiceModel.Description.WebScriptEndpoint> al servizio. Se non è necessario modificare la configurazione dell'endpoint, la sezione `<system.ServiceModel>` può essere rimossa completamente dal file Web.config del servizio. Il file Web.config contiene alcune impostazioni di ASP.NET che vengono usate da ConfigFreeClientPage.aspx. Se la situazione è diversa, il file Web.config potrebbe essere totalmente rimosso.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di eseguire le istruzioni di installazione nella [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione Xmlajaxservice come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Passare a `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (non aprire Configfreeclientpage nel browser dalla directory del progetto).  
  
> [!NOTE]
>  Quando si esegue questo esempio, assicurarsi che Autenticazione anonima e Autenticazione Windows non siano abilitate simultaneamente per la cartella ServiceModelSamples in IIS. Se così dovesse essere, disabilitare l'autenticazione Windows. Dopo aver eseguito l'esempio, abilitare l'autenticazione Windows ed eseguire "iisreset".  
  
## <a name="see-also"></a>Vedere anche  
 [Servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
