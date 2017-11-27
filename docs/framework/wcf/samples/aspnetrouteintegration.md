---
title: AspNetRouteIntegration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b54de1c495dee466475979db7e6ba8d8ff9cf55b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
In questo esempio viene descritto come ospitare un servizio REST di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizzando route ASP.NET. Il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio viene illustrata una versione indipendente di questo scenario e ne illustra l'implementazione del servizio in modo approfondito. Questo argomento descrive la funzionalità di integrazione ASP.NET. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] routing ASP.NET, vedere <xref:System.Web.Routing>.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] presenta una raccolta di clienti in modo orientato alle risorse/REST. In modo analogo a un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basato su SOAP, il servizio può essere ospitato in ASP.NET utilizzando un file con estensione svc. Tuttavia, spesso non si tratta della scelta consigliata per scenari HTTP perché richiede la presenza del file con estensione svc nell'URL del servizio. Inoltre, richiede la distribuzione di un file con estensione svc insieme alla libreria di servizi. È possibile evitare tali limitazioni ospitando il servizio mediante route ASP.NET, come illustrato nel presente esempio.  
  
 Nell'esempio il servizio viene ospitato in ASP.NET aggiungendo un oggetto <xref:System.ServiceModel.Activation.ServiceRoute> in un file Global.asax. <xref:System.ServiceModel.Activation.ServiceRoute> specifica il tipo di servizio ('Service' in questo caso), il tipo di factory dell'host del servizio da utilizzare per il servizio (<xref:System.ServiceModel.Activation.WebServiceHostFactory> in questo caso) e l'indirizzo HTTP di base per il servizio ('~/Customers' in questo caso).  
  
 In aggiunta a ciò, l'esempio include un file Web.config che aggiunge <xref:System.Web.Routing.UrlRoutingModule> (per attivare route ASP.NET) e include la configurazione per il servizio. In particolare, la configurazione imposta il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con un <xref:System.ServiceModel.Description.WebHttpEndpoint> predefinito che dispone dell'impostazione <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> configurata su `true`. Di conseguenza, l'infrastruttura [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una pagina automatica della Guida basata su HTML all'indirizzo `http://localhost/Customers/help`, che fornisce informazioni su come creare richieste HTTP per il servizio e come accedere alla risposta HTTP del servizio, quali un esempio di come i dettagli del cliente vengono rappresentati in XML e JSON.  
  
 La presentazione della raccolta di clienti (e, in termini più generali, di qualsiasi risorsa) in questo modo consente a un client di interagire con un servizio in modo uniforme utilizzando URI e richieste HTTP `GET`, `PUT`, `DELETE` e `POST`.  
  
 Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. È infatti possibile accedere al servizio usando altre classi .NET Framework come la channel factory [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio e [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio) viene illustrato come utilizzare queste classi per comunicare con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.  
  
 L'esempio è costituito da 3 progetti:  
  
 Servizio  
 Progetto di applicazione Web che include un servizio WCF HTTP ospitato in ASP.NET.  
  
 Client  
 Progetto di applicazione console che effettua chiamate al servizio.  
  
 Comuni  
 Libreria condivisa che contiene il tipo `Customer` utilizzato dal client e dal servizio. Quando viene eseguita l'applicazione console client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo all'integrazione di route ASP.NET in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Se non è già aperto, premere "CTRL + W, S" per aprire la **Esplora** finestra.  
  
4.  Dal **Esplora** windows, fare doppio clic sul **servizio** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta in modo che il **avviare Nuova istanza** menu di scelta rapida e selezionare **Avvia nuova istanza**.  Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5.  Dal **Esplora** windows, fare doppio clic sul **Client** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta in modo che il **Avvia nuovo Istanza** menu di scelta rapida e selezionare **Avvia nuova istanza**.  
  
6.  Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
7.  Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
8.  Premere MAIUSC + F5 per arrestare il debug del servizio e fare doppio clic sull'icona del server di sviluppo ASP.NET nell'Area di notifica Windows e selezionare **arrestare** dal menu di scelta rapida.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>Vedere anche
