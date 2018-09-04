---
title: Servizio HTTP di base
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 914ad5f04d980fd53cd07251461367356f00b4cc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516629"
---
# <a name="basic-http-service"></a>Servizio HTTP di base
In questo esempio viene illustrato come implementare un servizio basato su RPC su HTTP, - noto come servizio "POX" (Plain Old XML) usando il modello di programmazione REST di Windows Communication Foundation (WCF). Questo esempio è costituito da due componenti: un servizio HTTP WCF indipendente (Service.cs) e un'applicazione console (Program.cs) che crea il servizio ed effettua chiamate ad esso.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il servizio WCF espone 2 operazioni, `EchoWithGet` e `EchoWithPost`, che restituisce la stringa passata come input.  
  
 L'operazione `EchoWithGet` viene annotata con <xref:System.ServiceModel.Web.WebGetAttribute>, che indica che l'operazione elabora richieste HTTP `GET`. Poiché <xref:System.ServiceModel.Web.WebGetAttribute> non specifica in modo esplicito un <xref:System.UriTemplate>, l'operazione prevede che la stringa di input venga passata mediante un parametro della stringa di query con nome `s`. Si noti che il formato dell'URI che il servizio prevede di ricevere può essere personalizzato mediante la proprietà <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.  
  
 L'operazione `EchoWithPost` viene annotata con <xref:System.ServiceModel.Web.WebInvokeAttribute>, che l'indica che non si tratta di un'operazione `GET` (con effetti collaterali). Poiché <xref:System.ServiceModel.Web.WebInvokeAttribute> non specifica in modo esplicito un elemento `Method`, l'operazione elabora richieste HTTP `POST` con la stringa nel corpo della richiesta (ad esempio, in formato XML). Si noti che il metodo HTTP e il formato dell'URI per la richiesta possono essere personalizzati utilizzando rispettivamente le proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> e <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>.  
  
 Il file App.config configura il servizio WCF con un endpoint <xref:System.ServiceModel.Description.WebHttpEndpoint> predefinito in cui la proprietà <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> è impostata su `true`. Di conseguenza, l'infrastruttura WCF crea una pagina automatica della Guida basata su HTML in `http://localhost:8000/Customers/help` che fornisce informazioni su come creare richieste HTTP al servizio e come utilizzare la risposta del servizio HTTP.  
  
 Program.cs illustra come una factory canale WCF è utilizzabile per effettuare chiamate al servizio ed elaborare le risposte. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF. È inoltre possibile accedere al servizio utilizzando altre classi .NET Framework come <xref:System.Net.HttpWebRequest> e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [la selezione del formato automatica](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio e [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio) Mostra come usare queste classi per comunicare con un servizio WCF.  
  
 L'esempio è costituito da un servizio indipendente e da un client, entrambi in esecuzione in un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo al servizio Http di base. Per garantire l'esecuzione corretta dell'esempio, è necessario che l'avvio di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] venga eseguito come amministratore. Eseguire questa operazione facendo clic con il [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icona e selezionando **Esegui come amministratore** dal menu di scelta rapida.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere Ctrl+F5 per eseguire il progetto dell'applicazione console senza eseguirne il debug. Verrà visualizzata la finestra della console in cui saranno disponibili gli URI del servizio in esecuzione e della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
3.  Premere un tasto qualsiasi per terminare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>Vedere anche  
 [Selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [Servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md)
