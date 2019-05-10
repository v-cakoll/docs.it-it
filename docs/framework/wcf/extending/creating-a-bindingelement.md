---
title: Creazione di una classe BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 0c08494315f43f35f60d70abf643f596a013c302
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587323"
---
# <a name="creating-a-bindingelement"></a>Creazione di una classe BindingElement
Associazioni ed elementi di associazione (oggetti che estendono <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> e <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>rispettivamente) sono il luogo in cui il modello di applicazione Windows Communication Foundation (WCF) è associato con le channel factory e listener del canale. Senza associazioni, tramite i canali personalizzati richiede programmazione a livello di canale come descritto in [canale del servizio a livello di programmazione](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) e [programmazione a livello di canale Client](../../../../docs/framework/wcf/extending/client-channel-level-programming.md). Questo argomento vengono illustrati il requisito minimo per consentirne l'utilizzo del canale in WCF, lo sviluppo di un <xref:System.ServiceModel.Channels.BindingElement> per il canale e abilita l'uso dell'applicazione come descritto nel passaggio 4 della [canali emergenti](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="overview"></a>Panoramica  
 Creazione di un <xref:System.ServiceModel.Channels.BindingElement> per il canale consente agli sviluppatori di utilizzarlo in un'applicazione WCF. <xref:System.ServiceModel.Channels.BindingElement> gli oggetti possono essere utilizzati dal <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> classe connettere un'applicazione WCF al canale senza le informazioni sul tipo preciso del canale.  
  
 Una volta una <xref:System.ServiceModel.Channels.BindingElement> è stato creato, è possibile abilitare ulteriori funzionalità a seconda dei requisiti seguendo i passaggi rimanenti di sviluppo channel descritto nella [canali emergenti](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Aggiunta di un elemento di associazione.  
 Per implementare una classe <xref:System.ServiceModel.Channels.BindingElement> personalizzata, scrivere una classe che eredita da <xref:System.ServiceModel.Channels.BindingElement>. Ad esempio, se è stato sviluppato un elemento `ChunkingChannel` per suddividere i messaggi di grandi dimensioni in blocchi e assemblarli di nuovo sull'altra estremità, è possibile utilizzare questo canale in qualsiasi associazione implementando una classe <xref:System.ServiceModel.Channels.BindingElement> e configurando l'associazione per il relativo utilizzo. Nella restante parte di questo argomento, verrà utilizzato `ChunkingChannel` come esempio per illustrare i requisiti dell'implementazione di un elemento di associazione.  
  
 `ChunkingBindingElement` è responsabile della creazione di `ChunkingChannelFactory` e `ChunkingChannelListener`. Esegue l'override delle implementazioni dei metodi <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> e <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>, controlla che il parametro di tipo sia <xref:System.ServiceModel.Channels.IDuplexSessionChannel> (nell'esempio si tratta dell'unica forma del canale supportata da `ChunkingChannel`) e che gli altri elementi di associazione presenti nell'associazione supportino tale forma.  
  
 Il metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> controlla prima che la forma del canale richiesta possa essere creata e poi ottiene un elenco di azioni del messaggio da suddividere in blocchi. Crea quindi una nuova `ChunkingChannelFactory`, passando la channel factory interna (se si sta creando un elemento di associazione del trasporto, tale elemento è l'ultimo nello stack dell'associazione e pertanto deve necessariamente creare un listener del canale o una channel factory).  
  
 L'implementazione del metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> per creare `ChunkingChannelListener` e passare il listener del canale interno è simile.  
  
 Come ulteriore esempio di utilizzo di un canale di trasporto, il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) comprende l'override seguente.  
  
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
 I nuovi elementi di associazione possono sostituire o aumentare gli elementi di associazione presenti, aggiungendo nuovi trasporti, codifiche o protocolli di livello superiore. Per creare un nuovo elemento di associazione di protocollo, iniziare estendendo la classe <xref:System.ServiceModel.Channels.BindingElement>. Come minimo, è necessario quindi implementare il <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> e implementare le `ChannelProtectionRequirements` usando <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. In questo modo viene restituita la classe <xref:System.ServiceModel.Security.ChannelProtectionRequirements> per l'elemento di associazione.  Per altre informazioni, vedere <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 Il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> deve restituire una copia aggiornata dell'elemento di associazione. È consigliabile che gli autori dell'elemento di associazione implementino il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> utilizzando un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
#### <a name="transport-binding-elements"></a>Elementi di associazione del trasporto  
 Per creare un nuovo elemento di associazione del trasporto, estendere l'interfaccia <xref:System.ServiceModel.Channels.TransportBindingElement>. È necessario quindi implementare almeno il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> e la proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Deve restituire una copia aggiornata dell'elemento di associazione.  È consigliabile che gli autori dell'elemento di associazione implementino Clone mediante un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – La proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> restituisce lo schema URI per il protocollo di trasporto rappresentato dall'elemento di associazione. Ad esempio, il <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> e il <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> restituiscono "http" e "NET. TCP" dalle rispettive <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> proprietà.  
  
#### <a name="encoding-binding-elements"></a>Elementi di associazione di codifica  
 Per creare un nuovo elemento di associazione di codifica, iniziare estendendo la classe <xref:System.ServiceModel.Channels.BindingElement> e implementando la classe <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>. È necessario quindi implementare almeno i metodi <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> e <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> e la proprietà <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Restituisce una copia aggiornata dell'elemento di associazione. È consigliabile che gli autori dell'elemento di associazione implementino il metodo <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> utilizzando un costruttore di copia che chiami il costruttore di copia di base e che quindi duplichi i campi aggiuntivi in questa classe.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Restituisce una classe <xref:System.ServiceModel.Channels.MessageEncoderFactory> che fornisce un handle alla classe effettiva che implementa il nuovo codificatore e che deve estendere la classe <xref:System.ServiceModel.Channels.MessageEncoder>. Per altre informazioni, vedere <xref:System.ServiceModel.Channels.MessageEncoderFactory> e <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Restituisce la classe <xref:System.ServiceModel.Channels.MessageVersion> utilizzata in questa codifica, che rappresenta le versioni di SOAP e WS-Addressing utilizzate.  
  
 Per un elenco completo dei metodi e delle proprietà facoltative per gli elementi di associazione di codifica definiti dall'utente, vedere <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Per altre informazioni sulla creazione di un nuovo elemento di associazione, vedere [associazioni Creating User-Defined](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Dopo aver creato un elemento di associazione per il canale, tornare al [emergenti canali](../../../../docs/framework/wcf/extending/developing-channels.md) argomento per vedere se si desidera aggiungere il supporto di file di configurazione all'elemento di associazione, se e come aggiungere il supporto di pubblicazione dei metadati, e Se e come per costruire un'associazione definita dall'utente che usa l'elemento di associazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.BindingElement>
- [Sviluppo di canali](../../../../docs/framework/wcf/extending/developing-channels.md)
- [Trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
