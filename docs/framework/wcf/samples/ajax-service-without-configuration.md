---
title: Servizio AJAX senza configurazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13f74a69e05c419cc76cc8df8f58d3e3385ab35f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ajax-service-without-configuration"></a>Servizio AJAX senza configurazione
Questo esempio illustra come usare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per creare un servizio AJAX (ASP.NET Asynchronous JavaScript and XML) di base, ovvero un servizio al quale è possibile accedere usando codice JavaScript da un client browser Web senza usare alcuna impostazione di configurazione. Il servizio usa sintassi speciale nel file con estensione svc per abilitare automaticamente un endpoint AJAX.  
  
 Il supporto AJAX in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo `ScriptManager`. Per un esempio di utilizzo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vedere il [esempi Ajax](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene usato il servizio AJAX con il protocollo HTTP POST. Come descritto nel [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> viene utilizzato per ospitare il servizio.  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```  
  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aggiunge automaticamente un elemento <xref:System.ServiceModel.Description.WebScriptEndpoint> al servizio. Se è necessario apportare all'endpoint, senza modifiche alla configurazione di \<sistema. ServiceModel > sezione può essere rimossa completamente dal file Web. config per il servizio. Il file Web.config contiene alcune impostazioni di ASP.NET che vengono usate da ConfigFreeClientPage.aspx. Se la situazione è diversa, il file Web.config potrebbe essere totalmente rimosso.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di eseguire le istruzioni di installazione in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione ConfigFreeAjaxService.sln, come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Spostarsi alla pagina http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (non aprire ConfigFreeClientPage.aspx nel browser all'interno della directory del progetto).  
  
> [!NOTE]
>  Quando si esegue questo esempio, assicurarsi che Autenticazione anonima e Autenticazione Windows non siano abilitate simultaneamente per la cartella ServiceModelSamples in IIS. Se così dovesse essere, disabilitare l'autenticazione Windows. Dopo aver eseguito l'esempio, abilitare l'autenticazione Windows ed eseguire "iisreset".  
  
## <a name="see-also"></a>Vedere anche  
 [Servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
