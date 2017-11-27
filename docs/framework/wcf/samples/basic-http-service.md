---
title: Servizio HTTP di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf4d40bce37dea65f2a27421de736779e467e728
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="basic-http-service"></a>Servizio HTTP di base
In questo esempio viene illustrato come implementare un servizio basato su HTTP, basato su RPC - grazie alla funzionalità di cui per il servizio "POX" (Plain Old XML), utilizzando il [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] modello di programmazione REST. L'esempio è costituito da due componenti: un servizio HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] indipendente (Service.cs) e un'applicazione console (Program.cs) che crea il servizio ed effettua chiamate ad esso dirette.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espone 2 operazioni, ovvero `EchoWithGet` e `EchoWithPost`, che restituisce la stringa passata come input.  
  
 L'operazione `EchoWithGet` viene annotata con <xref:System.ServiceModel.Web.WebGetAttribute>, che indica che l'operazione elabora richieste HTTP `GET`. Poiché <xref:System.ServiceModel.Web.WebGetAttribute> non specifica in modo esplicito un <xref:System.UriTemplate>, l'operazione prevede che la stringa di input venga passata mediante un parametro della stringa di query con nome `s`. Si noti che il formato dell'URI che il servizio prevede di ricevere può essere personalizzato mediante la proprietà <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.  
  
 L'operazione `EchoWithPost` viene annotata con <xref:System.ServiceModel.Web.WebInvokeAttribute>, che l'indica che non si tratta di un'operazione `GET` (con effetti collaterali). Poiché <xref:System.ServiceModel.Web.WebInvokeAttribute> non specifica in modo esplicito un elemento `Method`, l'operazione elabora richieste HTTP `POST` con la stringa nel corpo della richiesta (ad esempio, in formato XML). Si noti che il metodo HTTP e il formato dell'URI per la richiesta possono essere personalizzati utilizzando rispettivamente le proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> e <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>.  
  
 Il file App.config configura il servizio WCF con un endpoint <xref:System.ServiceModel.Description.WebHttpEndpoint> predefinito in cui la proprietà <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> è impostata su `true`. Di conseguenza, l'infrastruttura di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una pagina automatica della Guida basata su HTM all'indirizzo `http://localhost:8000/Customers/help`, che fornisce informazioni su come creare richieste HTTP al servizio e su come utilizzare la risposta HTTP del servizio.  
  
 Program.cs illustra come una channel factory di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può essere utilizzata per effettuare chiamate al servizio ed elaborare le risposte. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. È inoltre possibile accedere al servizio utilizzando altre classi .NET Framework come <xref:System.Net.HttpWebRequest> e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio e [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio) viene illustrato come utilizzare queste classi per comunicare con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.  
  
 L'esempio è costituito da un servizio indipendente e da un client, entrambi in esecuzione in un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo al servizio Http di base. Per garantire l'esecuzione corretta dell'esempio, è necessario che l'avvio di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] venga eseguito come amministratore. Farlo facendo clic con il [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e selezionando **Esegui come amministratore** dal menu di scelta rapida.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere Ctrl+F5 per eseguire il progetto dell'applicazione console senza eseguirne il debug. Verrà visualizzata la finestra della console in cui saranno disponibili gli URI del servizio in esecuzione e della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
3.  Premere un tasto qualsiasi per terminare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>Vedere anche  
 [Selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [Servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md)
