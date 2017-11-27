---
title: Endpoint SOAP e HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9404d304302360b2be590c814d1f94cb46bd5f84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="soap-and-http-endpoints"></a>Endpoint SOAP e HTTP
In questo esempio viene illustrato come implementare un servizio basato su RPC e come esporlo nel formato SOAP e il "Plain Old XML" (POX) formato utilizzando il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modello di programmazione Web. Vedere il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) per ulteriori dettagli sul binding HTTP per il servizio. Questo esempio si concentra sui dettagli che riguardano l'esposizione dello stesso servizio su SOAP e HTTP tramite associazioni diverse.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Esposizione di un servizio RPC su SOAP e HTTP con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="discussion"></a>Discussione  
 Questo esempio è costituito da due componenti: un progetto di applicazione Web (Service) contenente un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un'applicazione console (Client) che richiama le operazioni del servizio usando associazioni SOAP e HTTP.  
  
 Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espone 2 operazioni, ovvero `GetData` e `PutData`, che eseguono l'eco della stringa passata come input. Le operazioni del servizio vengono annotate con <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>. Questi attributi controllano la proiezione HTTP di queste operazioni. Vengono inoltre annotate con <xref:System.ServiceModel.OperationContractAttribute>, consentendone l'esposizione su associazioni SOAP. Il metodo `PutData` del servizio genera un oggetto <xref:System.ServiceModel.Web.WebFaultException> che viene inviato di nuovo su HTTP usando il codice di stato HTTP e su SOAP come errore SOAP.  
  
 Il file Web.config configura il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con 3 endpoint:  
  
-   L'endpoint ~/service.svc/mex che espone i metadati del servizio per l'accesso da client basati su SOAP.  
  
-   L'endpoint ~/service.svc/http che consente ai client di accedere al servizio usando l'associazione HTTP.  
  
-   L'endpoint ~/service.svc/soap che consente ai client di accedere al servizio usando SOAP sull'associazione HTTP.  
  
 L'endpoint HTTP viene configurato con un endpoint standard<`webHttp`> con `helpEnabled` impostato su `true`. Di conseguenza, il servizio espone una pagina della Guida basata su XHTML in corrispondenza di ~/service.svc/http/help che i client basati su HTTP possono usare per accedere al servizio.  
  
 Il progetto client viene illustrato l'accesso al servizio tramite un proxy SOAP (generato tramite **Aggiungi riferimento al servizio**) e l'accesso del servizio utilizzando <xref:System.Net.WebClient>.  
  
 L'esempio è costituito da un servizio ospitato sul Web e da un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione per l'esempio relativo agli endpoint SOAP e HTTP.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Se non è già aperto, premere CTRL + W, S per aprire la **Esplora** finestra.  
  
4.  Dal **Esplora soluzioni** finestra, fare doppio clic sul **servizio** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta in modo che il **Avvia nuovo Istanza** menu di scelta rapida visualizzato. Fare clic su **Avvia nuova istanza**. Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5.  Da Esplora soluzioni, fare clic sul progetto Client e posizionare il cursore di **Debug** opzione del menu di scelta in modo che il **Avvia nuova istanza** menu di scelta rapida viene visualizzato. Fare clic su **Avvia nuova istanza**.  
  
6.  Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.  
  
7.  Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
8.  Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
9. Premere MAIUSC+F5 per interrompere il debug del servizio.  
  
10. Nell'Area di notifica Windows, fare doppio clic sull'icona del server di sviluppo ASP.NET e selezionare **arrestare** dal menu di scelta rapida.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
