---
title: Creazione di una classe BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 4b760f9373e64e153bd5a21469eb7a503283d35c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795820"
---
# <a name="creating-a-bindingelement"></a>Creazione di una classe BindingElement
Le associazioni e gli elementi di associazione, ovvero <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> gli <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>oggetti che estendono rispettivamente e, rappresentano la posizione in cui il modello di applicazione Windows Communication Foundation (WCF) è associato alle channel factory e ai listener del canale. Senza binding, l'utilizzo di canali personalizzati richiede la programmazione a livello di canale, come descritto in programmazione a livello di [canale del servizio](service-channel-level-programming.md) e programmazione a [livello di canale client](client-channel-level-programming.md). In questo argomento viene illustrato il requisito minimo per abilitare l'utilizzo del canale in WCF, lo <xref:System.ServiceModel.Channels.BindingElement> sviluppo di un per il canale e l'abilitazione dell'utilizzo dall'applicazione come descritto nel passaggio 4 dello [sviluppo di canali](developing-channels.md).  
  
## <a name="overview"></a>Panoramica  
 La creazione <xref:System.ServiceModel.Channels.BindingElement> di un per il canale consente agli sviluppatori di utilizzarlo in un'applicazione WCF. <xref:System.ServiceModel.Channels.BindingElement>gli oggetti possono essere utilizzati dalla <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> classe per connettere un'applicazione WCF al canale senza dover specificare le informazioni sul tipo esatte del canale.  
  
 Una volta <xref:System.ServiceModel.Channels.BindingElement> creato un, è possibile abilitare più funzionalità in base ai requisiti attenendosi alla procedura di sviluppo del canale rimanente descritta in [sviluppo di canali](developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Aggiunta di un elemento di associazione.  
 Per implementare una classe <xref:System.ServiceModel.Channels.BindingElement> personalizzata, scrivere una classe che eredita da <xref:System.ServiceModel.Channels.BindingElement>. Ad esempio, se è stato sviluppato un elemento `ChunkingChannel` per suddividere i messaggi di grandi dimensioni in blocchi e assemblarli di nuovo sull'altra estremità, è possibile utilizzare questo canale in qualsiasi associazione implementando una classe <xref:System.ServiceModel.Channels.BindingElement> e configurando l'associazione per il relativo utilizzo. Nella restante parte di questo argomento, verrà utilizzato `ChunkingChannel` come esempio per illustrare i requisiti dell'implementazione di un elemento di associazione.  
  
 `ChunkingBindingElement` è responsabile della creazione di `ChunkingChannelFactory` e `ChunkingChannelListener`. Esegue l'override delle implementazioni dei metodi <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> e <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>, controlla che il parametro di tipo sia <xref:System.ServiceModel.Channels.IDuplexSessionChannel> (nell'esempio si tratta dell'unica forma del canale supportata da `ChunkingChannel`) e che gli altri elementi di associazione presenti nell'associazione supportino tale forma.  
  
 Il metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> controlla prima che la forma del canale richiesta possa essere creata e poi ottiene un elenco di azioni del messaggio da suddividere in blocchi. Crea quindi una nuova `ChunkingChannelFactory`, passando la channel factory interna (se si sta creando un elemento di associazione del trasporto, tale elemento è l'ultimo nello stack dell'associazione e pertanto deve necessariamente creare un listener del canale o una channel factory).  
  
 L'implementazione del metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> per creare `ChunkingChannelListener` e passare il listener del canale interno è simile.  
  
 Come altro esempio di utilizzo di un canale di [trasporto, il trasporto: L'](../samples/transport-udp.md) esempio UDP fornisce la seguente sostituzione.  
  
 Nell'esempio, l'elemento di associazione è `UdpTransportBindingElement`, che deriva dalla classe <xref:System.ServiceModel.Channels.TransportBindingElement>. Esso esegue l'override dei metodi seguenti per creare le factory associate al canale.  
  
```csharp  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 Contiene inoltre membri per duplicare `BindingElement` e restituire lo schema (soap.udp).  
  
#### <a name="protocol-binding-elements"></a>Elementi di associazione di protocollo  
 I nuovi elementi di associazione possono sostituire o aumentare gli elementi di associazione presenti, aggiungendo nuovi trasporti, codifiche o protocolli di livello superiore. Per creare un nuovo elemento di associazione di protocollo, iniziare estendendo la classe <xref:System.ServiceModel.Channels.BindingElement>. Come minimo, è necessario implementare <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> e implementare l' `ChannelProtectionRequirements` oggetto utilizzando <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. In questo modo viene restituita la classe <xref:System.ServiceModel.Security.ChannelProtectionRequirements> per l'elemento di associazione.  Per altre informazioni, vedere <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 Il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> deve restituire una copia aggiornata dell'elemento di associazione. È consigliabile che gli autori dell'elemento di associazione implementino il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> utilizzando un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
#### <a name="transport-binding-elements"></a>Elementi di associazione del trasporto  
 Per creare un nuovo elemento di associazione del trasporto, estendere l'interfaccia <xref:System.ServiceModel.Channels.TransportBindingElement>. È necessario quindi implementare almeno il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> e la proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Deve restituire una copia aggiornata dell'elemento di associazione.  È consigliabile che gli autori dell'elemento di associazione implementino Clone mediante un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – La proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> restituisce lo schema URI per il protocollo di trasporto rappresentato dall'elemento di associazione. Ad esempio, <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> e restituiscono "http" e "NET. TCP" dalle rispettive <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> proprietà.  
  
#### <a name="encoding-binding-elements"></a>Elementi di associazione di codifica  
 Per creare un nuovo elemento di associazione di codifica, iniziare estendendo la classe <xref:System.ServiceModel.Channels.BindingElement> e implementando la classe <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>. È necessario quindi implementare almeno i metodi <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> e <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> e la proprietà <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Restituisce una copia aggiornata dell'elemento di associazione. È consigliabile che gli autori dell'elemento di associazione implementino il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> utilizzando un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
- [https://login.microsoftonline.com/common/](<xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>). Restituisce una classe <xref:System.ServiceModel.Channels.MessageEncoderFactory> che fornisce un handle alla classe effettiva che implementa il nuovo codificatore e che deve estendere la classe <xref:System.ServiceModel.Channels.MessageEncoder>. Per altre informazioni, vedere <xref:System.ServiceModel.Channels.MessageEncoderFactory> e <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>). Restituisce la classe <xref:System.ServiceModel.Channels.MessageVersion> utilizzata in questa codifica, che rappresenta le versioni di SOAP e WS-Addressing utilizzate.  
  
 Per un elenco completo dei metodi e delle proprietà facoltative per gli elementi di associazione di codifica definiti dall'utente, vedere <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Per ulteriori informazioni sulla creazione di un nuovo elemento di associazione, vedere [creazione di associazioni definite dall'utente](creating-user-defined-bindings.md).  
  
 Dopo aver creato un elemento di associazione per il canale, tornare all'argomento [sviluppo di canali](developing-channels.md) per verificare se si desidera aggiungere il supporto del file di configurazione all'elemento di associazione, se e come aggiungere il supporto per la pubblicazione di metadati e se e come costruire un'associazione definita dall'utente che utilizza l'elemento di associazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.BindingElement>
- [Sviluppo di canali](developing-channels.md)
- [Trasporto UDP](../samples/transport-udp.md)
