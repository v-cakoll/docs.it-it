---
title: Servizio AJAX con il protocollo HTTP POST
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2447f641748cdcc3419fda2a6ae8f02d68ed98e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-using-http-post"></a>Servizio AJAX con il protocollo HTTP POST
In questo esempio viene illustrato come utilizzare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per creare un servizio Asynchronous JavaScript and XML (AJAX) [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] che utilizza HTTP POST. È possibile accedere a questo servizio utilizzando il codice JavaScript di base da un client del browser Web. In questo esempio si basa il [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio; l'unica differenza tra i due esempi è l'utilizzo di HTTP POST invece di HTTP GET.  
  
 Il supporto AJAX in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo `ScriptManager`. Per un esempio di utilizzo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vedere il [esempi Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il servizio dell'esempio seguente è un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senza codice specifico per AJAX.  
  
 Se il <xref:System.ServiceModel.Web.WebInvokeAttribute> in un'operazione, viene applicato l'attributo o <xref:System.ServiceModel.Web.WebGetAttribute> non viene applicato l'attributo, viene utilizzato il verbo HTTP predefinito ("POST"). Le richieste POST sono più difficili da costruire rispetto alle richieste GET, ma non vengono memorizzate nella cache; utilizzare le richieste POST per tutte le operazioni in cui la memorizzazione nella cache non è appropriata.  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.  
  
 A differenza delle richieste GET, non è possibile richiamare servizi POST dal browser. Ad esempio, il passaggio ad http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 comporta un errore poiché il servizio POST si aspetta che i parametri `n1` e `n2` vengano inviati nel corpo del messaggio in formato JSON e non nell'URL.  
  
 La pagina Web PostAjaxClientPage.aspx del client contiene il codice ASP.NET per richiamare il servizio ogni qualvolta che l'utente fa clic su uno dei pulsanti di operazione nella pagina. Il servizio risponde esattamente come nel [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio, con la richiesta di recupero.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di eseguire le istruzioni di installazione [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione PostAjaxService.sln, come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Passare alla pagina http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (non aprire PostAjaxClientPage.aspx nel browser dalla directory del progetto).  
  
## <a name="see-also"></a>Vedere anche
