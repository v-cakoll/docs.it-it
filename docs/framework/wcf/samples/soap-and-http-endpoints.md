---
title: Endpoint SOAP e HTTP
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: f10b1aa4514aee50c0c0d17cabdb9516a3ca7584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144019"
---
# <a name="soap-and-http-endpoints"></a>Endpoint SOAP e HTTP
In questo esempio viene illustrato come implementare un servizio basato su RPC ed esporlo nel formato SOAP e nel formato "Plain Old XML" (POX) utilizzando il modello di programmazione Web WCF. Per altre informazioni sull'associazione HTTP per il servizio, vedere l'esempio di [servizio HTTP di base.](../../../../docs/framework/wcf/samples/basic-http-service.md) Questo esempio si concentra sui dettagli che riguardano l'esposizione dello stesso servizio su SOAP e HTTP tramite associazioni diverse.  
  
## <a name="demonstrates"></a>Dimostra  
 Esposizione di un servizio RPC tramite SOAP e HTTP tramite WCF.  
  
## <a name="discussion"></a>Discussione  
 Questo esempio è costituito da due componenti: un progetto di applicazione Web (Servizio) che contiene un servizio WCF e un'applicazione console (Client) che richiama le operazioni del servizio utilizzando le associazioni SOAP e HTTP.  
  
 Il servizio WCF espone`GetData` 2 `PutData` operazioni e , che riecheggiano la stringa passata come input. Le operazioni del servizio vengono annotate con <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>. Questi attributi controllano la proiezione HTTP di queste operazioni. Vengono inoltre annotate con <xref:System.ServiceModel.OperationContractAttribute>, consentendone l'esposizione su associazioni SOAP. Il metodo `PutData` del servizio genera un oggetto <xref:System.ServiceModel.Web.WebFaultException> che viene inviato di nuovo su HTTP usando il codice di stato HTTP e su SOAP come errore SOAP.  
  
 Il file Web.config configura il servizio WCF con 3 endpoint:  
  
- L'endpoint ~/service.svc/mex che espone i metadati del servizio per l'accesso da client basati su SOAP.  
  
- L'endpoint ~/service.svc/http che consente ai client di accedere al servizio usando l'associazione HTTP.  
  
- L'endpoint ~/service.svc/soap che consente ai client di accedere al servizio usando SOAP sull'associazione HTTP.  
  
 L'endpoint HTTP è `webHttp` configurato con un `helpEnabled` <`true`> endpoint standard impostato su . Di conseguenza, il servizio espone una pagina della Guida basata su XHTML in corrispondenza di ~/service.svc/http/help che i client basati su HTTP possono usare per accedere al servizio.  
  
 Il progetto client illustra l'accesso al servizio utilizzando un proxy SOAP (generato tramite **Aggiungi riferimento**al servizio ) e l'accesso al servizio tramite <xref:System.Net.WebClient>.  
  
 L'esempio è costituito da un servizio ospitato sul Web e da un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1. Aprire la soluzione per l'esempio relativo agli endpoint SOAP e HTTP.  
  
2. Premere CTRL+MAIUSC+B per compilare la soluzione.  
  
3. Se non è già aperto, premere CTRL-W, S per aprire la finestra **Esplora soluzioni.**  
  
4. Nella finestra **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **Di servizio** e posizionare il cursore sull'opzione di menu di scelta rapida **Debug** in modo che venga visualizzato il menu di scelta rapida Avvia **nuova istanza.** Fare clic su **Avvia nuova istanza**. Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5. Nelle finestre Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client e posizionare il cursore sull'opzione del menu di scelta rapida **Debug** in modo che venga visualizzato il menu di scelta rapida **Avvia nuova istanza.** Fare clic su **Avvia nuova istanza**.  
  
6. Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.  
  
7. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
8. Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
9. Premere MAIUSC+F5 per interrompere il debug del servizio.  
  
10. Nell'area di notifica di Windows, fare clic con il pulsante destro del mouse sull'icona del server di sviluppo ASP.NET e scegliere **Interrompi** dal menu di scelta rapida.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
