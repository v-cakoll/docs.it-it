---
title: Servizio risorse di base
ms.date: 03/30/2017
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
ms.openlocfilehash: 62b2b863f38647e81468065fd69fc4933afc5b16
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="basic-resource-service"></a>Servizio risorse di base
In questo esempio viene illustrato come implementare un servizio basato su HTTP utilizzando il modello di programmazione REST di Windows Communication Foundation (WCF) che espone una raccolta di clienti che supporta il recupero, aggiungere, eliminare e sostituire operazioni. Questo esempio è costituito da 2 componenti - un servizio HTTP WCF indipendente (Service.cs) e un'applicazione console (program.cs) che crea il servizio ed effettua chiamate ad esso.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il servizio WCF presenta una raccolta di clienti in modo risorse orientata ai servizi/REST. In breve, ciò significa disporre di URI univoci per la raccolta di clienti e per ogni cliente nella raccolta. Il servizio supporta l'invio di un HTTP `GET` all'URI della raccolta per recuperare l'intera raccolta e di HTTP `POST` all'URI della raccolta per aggiungere un nuovo cliente alla raccolta. Anche a livello di URI per singolo cliente, supporta `GET` HTTP per ottenere i dettagli del cliente, `PUT` HTTP per sostituire i dettagli del cliente e `DELETE` HTTP per rimuovere il cliente dalla raccolta. Quando un nuovo cliente viene aggiunto alla raccolta, il servizio gli assegna un URI univoco e lo archivia come parte dei dettagli del cliente. Inoltre, comunica l'URI al client utilizzando l'intestazione HTTP relativa al percorso della risposta.  
  
 Il file App.config configura il servizio WCF con un endpoint <xref:System.ServiceModel.Description.WebHttpEndpoint> predefinito in cui la proprietà <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> è impostata su `true`. Di conseguenza, WCF crea una pagina automatica della Guida basati su HTML all'indirizzo `http://localhost:8000/Customers/help` che fornisce informazioni su come costruire HTTP richieste al servizio e come accedere alla risposta HTTP del servizio, ad esempio, un esempio del modo in cui i dettagli del cliente rappresentati in XML e JSON.  
  
 La presentazione della raccolta di clienti (e, in termini più generali, di qualsiasi risorsa) in questo modo consente al client di interagire con essa in modo uniforme utilizzando URI e HTTP `GET`, `PUT`, `DELETE` e `POST`. Il file Program.cs illustra come è possibile creare tale client utilizzando <xref:System.Net.HttpWebRequest>. Si noti che questo è solo un modo per accedere a un servizio WCF REST. È infatti possibile accedere al servizio utilizzando altre classi .NET Framework come la <xref:System.ServiceModel.ChannelFactory> e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio e il [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio) viene illustrato come usare queste classi per comunicare con un servizio WCF.  
  
 L'esempio è costituito da un servizio indipendente e da un client, entrambi in esecuzione in un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo al servizio risorse di base. Per garantire l'esecuzione corretta dell'esempio, è necessario che l'avvio di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] venga eseguito come amministratore. Farlo facendo clic con il [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e selezionando **Esegui come amministratore** dal menu di scelta rapida.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere Ctrl+F5 per eseguire l'applicazione console. Verrà visualizzata la finestra della console in cui saranno disponibili gli URI del servizio in esecuzione e della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
3.  Premere un tasto qualsiasi per terminare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## <a name="see-also"></a>Vedere anche  
 [Servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md)  
 [Selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md)
