---
title: Servizio AJAX con il protocollo HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 560739c576965d597010a6885b53c7905aaeb8e7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716187"
---
# <a name="ajax-service-using-http-post"></a>Servizio AJAX con il protocollo HTTP POST

In questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio AJAX (ASP.NET Asynchronous JavaScript and XML) che utilizza HTTP POST. È possibile accedere a questo servizio utilizzando il codice JavaScript di base da un client del browser Web. Questo esempio si basa sull'esempio di [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) . l'unica differenza tra i due esempi è l'uso di HTTP POST anziché HTTP GET.

Il supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo `ScriptManager`. Per un esempio di utilizzo di WCF con ASP.NET AJAX, vedere gli [esempi di AJAX](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Il servizio nell'esempio seguente è un servizio WCF senza codice specifico per AJAX.

Se l'attributo <xref:System.ServiceModel.Web.WebInvokeAttribute> viene applicato a un'operazione o l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non viene applicato, viene utilizzato il verbo HTTP predefinito ("POST"). Le richieste POST sono più difficili da costruire rispetto alle richieste GET, ma non vengono memorizzate nella cache; utilizzare le richieste POST per tutte le operazioni in cui la memorizzazione nella cache non è appropriata.

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

A differenza delle richieste GET, non è possibile richiamare servizi POST dal browser. Se ad esempio si passa a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` genera un errore, perché il servizio POST prevede che i parametri `n1` e `n2` vengano inviati nel corpo del messaggio in formato JSON e non nell'URL.

La pagina Web PostAjaxClientPage.aspx del client contiene il codice ASP.NET per richiamare il servizio ogni qualvolta che l'utente fa clic su uno dei pulsanti di operazione nella pagina. Il servizio risponde in modo analogo all'esempio di [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , con la richiesta GET.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di eseguire le istruzioni di installazione [una sola volta la procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Compilare la soluzione PostAjaxService. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Passare a `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (non aprire PostAjaxClientPage. aspx nel browser dalla directory del progetto).
