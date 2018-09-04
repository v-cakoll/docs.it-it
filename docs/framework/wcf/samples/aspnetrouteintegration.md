---
title: AspNetRouteIntegration
ms.date: 03/30/2017
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
ms.openlocfilehash: 8d9a0710e5106cbc3d02a06e81f4f8ed9ae3e03b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561832"
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
In questo esempio viene illustrato come ospitare un servizio REST di Windows Communication Foundation (WCF) mediante route ASP.NET. Il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio viene illustrata una versione indipendente di questo scenario e ne illustra l'implementazione del servizio in modo approfondito. Questo argomento descrive la funzionalità di integrazione ASP.NET. Per altre informazioni sul Routing di ASP.NET, vedere <xref:System.Web.Routing>.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il servizio WCF espone una raccolta di clienti in modo risorse-oriented/REST. Proprio come un servizio WCF basato su SOAP, il servizio può essere ospitato in ASP.NET utilizzando un file con estensione svc. Tuttavia, spesso non si tratta della scelta consigliata per scenari HTTP perché richiede la presenza del file con estensione svc nell'URL del servizio. Inoltre, richiede la distribuzione di un file con estensione svc insieme alla libreria di servizi. È possibile evitare tali limitazioni ospitando il servizio mediante route ASP.NET, come illustrato nel presente esempio.  
  
 Nell'esempio il servizio viene ospitato in ASP.NET aggiungendo un oggetto <xref:System.ServiceModel.Activation.ServiceRoute> in un file Global.asax. <xref:System.ServiceModel.Activation.ServiceRoute> specifica il tipo di servizio ('Service' in questo caso), il tipo di factory dell'host del servizio da utilizzare per il servizio (<xref:System.ServiceModel.Activation.WebServiceHostFactory> in questo caso) e l'indirizzo HTTP di base per il servizio ('~/Customers' in questo caso).  
  
 In aggiunta a ciò, l'esempio include un file Web.config che aggiunge <xref:System.Web.Routing.UrlRoutingModule> (per attivare route ASP.NET) e include la configurazione per il servizio. In particolare, la configurazione consente di configurare il servizio WCF con un valore predefinito <xref:System.ServiceModel.Description.WebHttpEndpoint> con il <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> se si imposta su `true`. Di conseguenza, l'infrastruttura WCF crea una pagina automatica della Guida basata su HTML in `http://localhost/Customers/help` che fornisce informazioni su come costruire HTTP richieste al servizio e come accedere alla risposta del servizio HTTP, ad esempio, un esempio di come il cliente i dettagli sono rappresentati in XML e JSON.  
  
 La presentazione della raccolta di clienti (e, in termini più generali, di qualsiasi risorsa) in questo modo consente a un client di interagire con un servizio in modo uniforme utilizzando URI e richieste HTTP `GET`, `PUT`, `DELETE` e `POST`.  
  
 Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF. È anche possibile accedere al servizio utilizzando altre classi di .NET Framework, ad esempio la channel factory WCF e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio e il [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio) viene illustrato come utilizzare queste classi per comunicare con un servizio WCF.  
  
 L'esempio è costituito da 3 progetti:  
  
 Service  
 Progetto di applicazione Web che include un servizio WCF HTTP ospitato in ASP.NET.  
  
 Client  
 Progetto di applicazione console che effettua chiamate al servizio.  
  
 Common  
 Libreria condivisa che contiene il tipo `Customer` utilizzato dal client e dal servizio. Quando viene eseguita l'applicazione console client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo all'integrazione di route ASP.NET in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Se non è già aperto, premere "CTRL + W, S" per aprire la **Esplora soluzioni** finestra.  
  
4.  Dal **Esplora soluzioni** windows, fare doppio clic sul **servizio** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta rapida in modo che il **Start Nuova istanza** menu di scelta rapida viene visualizzata e selezionare **Avvia nuova istanza**.  Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5.  Dal **Esplora soluzioni** windows, fare doppio clic sui **Client** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta rapida in modo che il **Avvia nuovo Istanza** menu di scelta rapida viene visualizzata e selezionare **Avvia nuova istanza**.  
  
6.  Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
7.  Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
8.  Premere MAIUSC+F5 per arrestare il debug del servizio e nell'Area di notifica Windows, fare doppio clic sull'icona del server di sviluppo ASP.NET e selezionare **arrestare** dal menu di scelta rapida.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>Vedere anche
