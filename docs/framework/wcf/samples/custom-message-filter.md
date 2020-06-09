---
title: Filtro messaggi personalizzato
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 0e4da0f2283fd537afe3cacdddfb36c327cfd3b4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600044"
---
# <a name="custom-message-filter"></a>Filtro messaggi personalizzato
In questo esempio viene illustrato come sostituire i filtri messaggi utilizzati da Windows Communication Foundation (WCF) per inviare messaggi agli endpoint.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Quando il primo messaggio su un canale arriva al server, il server deve determinare quale degli endpoint associati all'URI (se presenti) deve ricevere il messaggio. Questo processo viene controllato dagli oggetti <xref:System.ServiceModel.Dispatcher.MessageFilter> allegati a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.  
  
 Ogni endpoint di un servizio ha un solo <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>. La classe <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> è dotata delle proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> e <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>. L'unione di questi due filtri è il filtro messaggi utilizzato per quell'endpoint.  
  
 Per impostazione predefinita, la proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> per un endpoint corrisponde a qualsiasi messaggio indirizzato a un indirizzo che corrisponde alla classe <xref:System.ServiceModel.EndpointAddress> dell'endpoint del servizio. Per impostazione predefinita, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> per un endpoint controlla l'azione del messaggio in arrivo e corrisponde a qualsiasi messaggio con un'azione che corrisponde a una delle azioni delle operazioni del contratto dell'endpoint di servizio ( `IsInitiating` = `true` vengono considerate solo le azioni). Di conseguenza, per impostazione predefinita il filtro per un endpoint corrisponde solo se l'intestazione di destinazione del messaggio rappresenta la classe <xref:System.ServiceModel.EndpointAddress> dell'endpoint e l'azione del messaggio corrisponde a una delle azioni dell'operazione dell'endpoint.  
  
 Questi filtri possono essere modificati utilizzando un comportamento. Nell'esempio, il servizio crea un'interfaccia <xref:System.ServiceModel.Description.IEndpointBehavior> che sostituisce le proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> e <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> nella classe <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 Vengono definiti due filtri per l'indirizzo:  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 `FilteringEndpointBehavior` è reso configurabile e consente due variazioni diverse.  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 La variazione 1 corrisponde solo agli indirizzi che contengono una 'e' (ma che sono dotati di qualsiasi azione), mentre la variazione 2 corrisponde solo agli indirizzi a cui manca una 'e':  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 Il servizio registra il nuovo comportamento nel file di configurazione:  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 Il servizio quindi crea le configurazioni `endpointBehavior` per ogni variazione:  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 L'endpoint del servizio infine fa riferimento a uno degli elementi `behaviorConfigurations`:  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 L'implementazione dell'applicazione client è semplice: crea due canali sull'URI del servizio passando quel valore come il secondo parametro (`via`) su <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> e invia un solo messaggio su ogni canale, utilizzando però indirizzi endpoint diversi per ognuno. Di conseguenza, i messaggi in uscita dal client hanno designazioni di destinazione diverse e il server risponde appropriatamente, come dimostrato dall'output del client:  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 La commutazione della variazione nel file di configurazione del server determina lo scambio del filtro e la visualizzazione da parte del client del comportamento contrario (il messaggio a `urn:e` ha esito positivo, mentre il messaggio a `urn:a` ha esito negativo).  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).  
  
2. Per eseguire l'esempio in una configurazione a computer singolo, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione tra computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md) e modificare la riga seguente in client.cs.  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     Sostituire localhost con il nome del server.  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
