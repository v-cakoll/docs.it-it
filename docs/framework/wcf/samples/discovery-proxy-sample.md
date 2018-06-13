---
title: Esempio relativo al proxy di individuazione
ms.date: 03/30/2017
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
ms.openlocfilehash: e9cbfcb717f502a849d4d508d13df6c00b95db58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33503184"
---
# <a name="discovery-proxy-sample"></a>Esempio relativo al proxy di individuazione
Questo esempio mostra come creare un'implementazione di un proxy di individuazione per archiviare informazioni sui servizi esistenti e come i client possono eseguire una query su tale proxy per ricevere informazioni. L'esempio è costituito da tre progetti:  
  
-   **Servizio**: un semplice servizio di calcolatrice di Windows Communication Foundation (WCF) che effettua la registrazione con il proxy di individuazione.  
  
-   **Proxy di individuazione**: l'implementazione di un servizio proxy di individuazione.  
  
-   **Client**: applicazione client WCF che chiama il proxy di individuazione per la ricerca per i servizi.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Implementazione di un proxy di individuazione  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## <a name="discoveryproxy"></a>DiscoveryProxy  
 Nel metodo `Main` del file Program.cs, l'esempio mostra come viene ospitato un servizio di tipo <xref:System.ServiceModel.Discovery.DiscoveryProxy>. Vengono esposti due endpoint, uno di tipo <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> e un altro di tipo <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>. Entrambi gli endpoint utilizzano TCP come trasporto. <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> è in ascolto su un URI specificato dal parametro `probeEndpointAddress`, ovvero sia dove i client possono inviare messaggi del probe per eseguire una query sul proxy per i dati. <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> è in ascolto su un URI specificato dal parametro `announcementEndpointAddress`. Si tratta di dove il proxy è in ascolto degli annunci. Quando viene ricevuto un annuncio online, il proxy aggiunge il servizio alla cache e quando viene ricevuto un annuncio offline il servizio viene rimosso dalla cache.  
  
 DiscoveryProxy.cs contiene l'implementazione di <xref:System.ServiceModel.Discovery.DiscoveryProxy>. Il proxy deve ereditare dalla classe <xref:System.Object> e richiede un'implementazione di <xref:System.Runtime.Remoting.Messaging.AsyncResult>. Durante la creazione di istanze, il proxy crea un nuovo <xref:System.Collections.Generic.Dictionary%602>, utilizzato per archiviare elementi noti.  
  
 Il file è diviso in due aree, metodi della cache del proxy e implementazione del proxy di individuazione. L'area dei metodi della cache del proxy contiene metodi utilizzati per aggiornare <xref:System.Collections.Generic.Dictionary%602>, eseguire query su <xref:System.Collections.Generic.Dictionary%602> e stampare dati per gli utenti. L'area di implementazione del proxy di individuazione contiene i metodi ignorati richiesti per la funzionalità di annuncio e probe. Tali metodi definiscono le azioni intraprese da un proxy dopo avere ricevuto un annuncio online, un annuncio offline o un messaggio del probe.  
  
## <a name="service"></a>Service  
 Nel file Program.cs nel progetto Service, lo stesso URI viene utilizzato per l'endpoint dell'annuncio come proxy di individuazione. Ciò si verifica perché il servizio utilizza l'endpoint per l'invio degli annunci, mentre il proxy lo utilizza per riceverli. Il servizio utilizza <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> e aggiunge un endpoint relativo agli annunci.  
  
## <a name="client"></a>Client  
 Il progetto Client utilizza lo stesso URI per l'endpoint del probe del proxy. Ciò si verifica perché i probe in questo scenario vengono trasmessi in unicast in modo specifico all'endpoint disponibile nel proxy. Il client si connette a questo indirizzo conosciuto, quindi esegue query per il servizio. Una volta individuato il servizio, effettua la connessione.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Caricare la soluzione del progetto in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e compilare il progetto.  
  
2.  Eseguire prima l'applicazione del proxy di individuazione, generato in [directory soluzione di base]\DiscoveryProxy\bin\debug. Il proxy di individuazione deve essere eseguito per primo perché gli endpoint relativi agli annunci TCP devono essere attivi affinché il servizio possa inviare i propri annunci.  
  
3.  In secondo luogo, eseguire prima l'applicazione del servizio, generata in [directory soluzione di base]\Service\bin\debug. All'avvio, il servizio invia un annuncio all'endpoint degli annunci del proxy di individuazione e tale annuncio viene registrato nella cache del proxy.  
  
4.  In seguito, eseguire prima l'applicazione client, generata in [directory soluzione di base]\Client\bin\debug. Il client esegue una query sul proxy, ottiene l'indirizzo del servizio, quindi si connette al servizio.  
  
5.  Infine, terminare il client, il servizio e quindi il proxy. Il proxy deve essere in esecuzione per ricevere l'annuncio offline del servizio.  
  
## <a name="see-also"></a>Vedere anche
