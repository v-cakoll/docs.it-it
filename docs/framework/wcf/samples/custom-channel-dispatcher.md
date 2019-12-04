---
title: Dispatcher di canali personalizzati
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 00caa5eda37e5da9462286e71bbdbc2ff50d5081
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716866"
---
# <a name="custom-channel-dispatcher"></a>Dispatcher di canali personalizzati
In questo esempio viene descritto come compilare lo stack di canali in modo personalizzato implementando direttamente <xref:System.ServiceModel.ServiceHostBase> e come creare un dispatcher del canale personalizzato in un ambiente host Web. Il dispatcher del canale interagisce con <xref:System.ServiceModel.Channels.IChannelListener> per accettare canali e recupera messaggi dallo stack di canali. Questo esempio fornisce anche un esempio di base che illustra come compilare uno stack di canali in un ambiente host Web tramite <xref:System.ServiceModel.Activation.VirtualPathExtension>.  
  
## <a name="custom-servicehostbase"></a>ServiceHostBase personalizzato  
 In questo esempio viene implementato il tipo di base <xref:System.ServiceModel.ServiceHostBase> anziché <xref:System.ServiceModel.ServiceHost> per illustrare come sostituire l'implementazione dello stack Windows Communication Foundation (WCF) con un livello di gestione dei messaggi personalizzato all'inizio dello stack dei canali. Viene eseguito l'override del metodo virtuale <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> per compilare i listener del canale e il dispatcher del canale.  
  
 Per implementare un servizio ospitato sul Web, ottenere l'estensione del servizio <xref:System.ServiceModel.Activation.VirtualPathExtension> dalla raccolta <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> e aggiungerla a <xref:System.ServiceModel.Channels.BindingParameterCollection> in modo che il livello di trasporto sia in grado di configurare il listener del canale in base alle impostazioni dell'ambiente host, ovvero le impostazioni Internet Information Services (IIS)/servizio di attivazione dei processi di Windows.  
  
## <a name="custom-channel-dispatcher"></a>Dispatcher di canali personalizzati  
 Il dispatcher del canale personalizzato estende il tipo <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>. Tale tipo implementa la logica di programmazione relativa al livello del canale. In questo esempio, solo <xref:System.ServiceModel.Channels.IReplyChannel> viene supportato per il modello di scambio di messaggi request/reply, ma il dispatcher del canale personalizzato può essere esteso facilmente ad altri tipi di canale.  
  
 Il dispatcher apre innanzitutto il listener del canale, quindi accetta il canale di risposta singleton. Con il canale, inizia a inviare messaggi (richieste) in un ciclo infinito. Per ogni richiesta, crea un messaggio di risposta e lo restituisce al client.  
  
## <a name="creating-a-response-message"></a>Creazione di un messaggio di risposta  
 L'elaborazione del messaggio viene implementata nel tipo `MyServiceManager`. Nel metodo `HandleRequest`, l'intestazione `Action` del messaggio viene dapprima controllata per verificare se la richiesta è supportata. È stata definita un'azione SOAP predefinita "http://tempuri.org/HelloWorld/Hello" per fornire filtri messaggi. Questa operazione è simile al concetto di contratto di servizio nell'implementazione WCF di <xref:System.ServiceModel.ServiceHost>.  
  
 Nel caso dell'azione SOAP corretta, l'esempio recupera i dati del messaggio richiesti e genera una risposta corrispondente alla richiesta in modo analogo a quanto si verifica nel caso di <xref:System.ServiceModel.ServiceHost>.  
  
 In questo caso, il verbo HTTP-GET viene gestito in modo speciale restituendo un messaggio HTML personalizzato, affinché sia possibile accedere al servizio da un browser per verificarne la corretta compilazione. Se l'azione SOAP non corrisponde, restituire un messaggio di errore per indicare che la richiesta non è supportata.  
  
 Il client di questo esempio è un normale client WCF che non presuppone alcuna parte del servizio. Il servizio è quindi appositamente progettato per trovare la corrispondenza con i risultati di una normale implementazione di WCF<xref:System.ServiceModel.ServiceHost>. Di conseguenza, nel client viene richiesto solo un contratto di servizio.  
  
## <a name="using-the-sample"></a>Utilizzo dell'esempio  
 L'esecuzione dell'applicazione client in modo diretto produce l'output seguente.  
  
```output  
Client is talking to a request/reply WCF service.   
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 È inoltre possibile accedere al servizio da un browser in modo che un messaggio HTTP-GET venga elaborato nel server. In questo modo, verrà restituito testo HTML formattato in modo corretto.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
