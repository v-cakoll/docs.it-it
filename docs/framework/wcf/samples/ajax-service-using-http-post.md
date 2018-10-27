---
title: Servizio AJAX con il protocollo HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: df199b40a4a9ebb9a36cea7234b484273348cd9e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192798"
---
# <a name="ajax-service-using-http-post"></a>Servizio AJAX con il protocollo HTTP POST
Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizio Asynchronous JavaScript and XML (AJAX) che utilizza HTTP POST. È possibile accedere a questo servizio utilizzando il codice JavaScript di base da un client del browser Web. In questo esempio si basa sul [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio; l'unica differenza tra i due è l'uso di HTTP POST anziché HTTP GET.  
  
 Supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il `ScriptManager` controllo. Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il servizio nell'esempio seguente è un servizio WCF senza codice AJAX specifico.  
  
 Se il <xref:System.ServiceModel.Web.WebInvokeAttribute> attributo è applicato a un'operazione, o <xref:System.ServiceModel.Web.WebGetAttribute> attributo non viene applicato, viene utilizzato il verbo HTTP predefinito ("POST"). Le richieste POST sono più difficili da costruire rispetto alle richieste GET, ma non vengono memorizzate nella cache; utilizzare le richieste POST per tutte le operazioni in cui la memorizzazione nella cache non è appropriata.  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.  
  
 A differenza delle richieste GET, non è possibile richiamare servizi POST dal browser. Ad esempio, il passaggio a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` genera un errore, poiché il servizio POST si aspetta che i `n1` e `n2` parametri da inviare nel corpo del messaggio in formato JSON e non nell'URL.  
  
 La pagina Web PostAjaxClientPage.aspx del client contiene il codice ASP.NET per richiamare il servizio ogni qualvolta che l'utente fa clic su uno dei pulsanti di operazione nella pagina. Il servizio risponde esattamente come nel [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio, con la richiesta GET.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di eseguire le istruzioni di installazione [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione Postajaxservice come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Passare a `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (non aprire Postajaxclientpage nel browser dalla directory del progetto).
