---
title: Accesso ai servizi tramite client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c8329832-bf66-4064-9034-bf39f153fc2d
ms.openlocfilehash: 001f30d7a0dde952a7d18bfbc50f2c3622287406
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576551"
---
# <a name="accessing-services-using-a-client"></a>Accesso ai servizi tramite client
Le applicazioni client devono creare, configurare e usare oggetti client o canale WCF per comunicare con i servizi. Nell'argomento [Panoramica client WCF](../wcf-client-overview.md) viene fornita una panoramica degli oggetti e dei passaggi necessari per creare oggetti client e canale di base e per utilizzarli.  
  
 In questo argomento vengono fornite informazioni dettagliate su alcuni dei problemi relativi ad applicazioni client e oggetti client e canale, che possono essere utili a seconda dello scenario.  
  
## <a name="overview"></a>Panoramica  
 In questo argomento vengono descritti il comportamento e i problemi relativi a:  
  
- Durata di canali e sessioni.  
  
- Gestione delle eccezioni.  
  
- Problemi che causano blocchi.  
  
- Inizializzazione interattiva dei canali.  
  
### <a name="channel-and-session-lifetimes"></a>Durata di canali e sessioni  
 Le applicazioni Windows Communication Foundation (WCF) includono due categorie di canali, datagramma e con sessione.  
  
 Un canale di *datagramma* è un canale in cui tutti i messaggi sono non correlati. Con un canale di datagramma, l'eventuale esito negativo di un'operazione di input o di output non ha di norma alcun effetto sulla successiva operazione ed è possibile riutilizzare lo stesso canale. Ne consegue che i canali di datagramma non hanno in genere esito negativo.  
  
 I canali con *sessione* , tuttavia, sono canali con una connessione all'altro endpoint. I messaggi in una sessione su uno dei lati vengono sempre correlati alla stessa sessione sull'altro lato. Inoltre, perché una sessione possa essere considerata riuscita, entrambi i partecipanti a essa devono concordare sul fatto che i requisiti della conversazione siano stati soddisfatti. In caso contrario, il canale con sessione può avere esito negativo.  
  
 Aprire i client in modo esplicito o implicito chiamando la prima operazione.  
  
> [!NOTE]
> Tentare di rilevare esplicitamente i canali con sessione in errore non è in genere utile, poiché il momento in cui si riceve la notifica dipende dall'implementazione della sessione. Poiché, ad esempio, la classe <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> (con la sessione affidabile disattivata) fa emergere la sessione della connessione TCP, se si è in ascolto dell'evento <xref:System.ServiceModel.ICommunicationObject.Faulted?displayProperty=nameWithType> sul servizio o sul client, è probabile che si riceva una notifica immediata in caso di errore di rete. Le sessioni affidabili (stabilite da associazioni in cui la classe <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> è attivata) sono però progettate per isolare i servizi da piccoli errori di rete. Se la sessione può essere ristabilita entro un periodo di tempo ragionevole, la stessa associazione, configurata per sessioni affidabili, potrebbe non generare errori fino a quando l'interruzione non dura per un periodo di tempo più lungo.  
  
 La maggior parte delle associazioni fornite dal sistema (che espongono canali al livello di applicazione) usa sessioni per impostazione predefinita, diversamente dall'associazione <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [Using Sessions](../using-sessions.md).  
  
### <a name="the-proper-use-of-sessions"></a>Utilizzo corretto delle sessioni  
 Le sessioni offrono un modo per sapere se l'intero scambio di messaggi è completo e se entrambi i lati lo considerano riuscito. È consigliabile che un'applicazione chiamante apra il canale, lo utilizzi e lo chiuda all'interno di un unico blocco try. Se un canale di sessione è aperto, il metodo <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> viene chiamato una volta e la chiamata viene restituita correttamente, la sessione ha esito positivo. Per esito positivo si intende, in questo caso, che tutto il recapito garantisce che l'associazione specificata è stata soddisfatta e che l'altro lato non ha chiamato <xref:System.ServiceModel.ICommunicationObject.Abort%2A?displayProperty=nameWithType> sul canale prima di chiamare <xref:System.ServiceModel.ICommunicationObject.Close%2A>.  
  
 Nella sezione seguente viene fornito un esempio di tale approccio client.  
  
### <a name="handling-exceptions"></a>Gestione delle eccezioni  
 La gestione di eccezioni nelle applicazioni client è semplice. Se un canale viene aperto, usato e chiuso all'interno di un blocco try, la conversazione ha avuto esito positivo, a meno che non venga generata un'eccezione. In genere, se viene generata un'eccezione, la conversazione viene interrotta.  
  
> [!NOTE]
> `using`Non è consigliabile usare l'istruzione ( `Using` in Visual Basic). poiché la fine dell'istruzione `using` può causare eccezioni che possono mascherare altre eccezioni che potrebbe essere necessario conoscere. Per ulteriori informazioni, vedere [utilizzare Close and Abort per rilasciare le risorse client WCF](../samples/use-close-abort-release-wcf-client-resources.md).  
  
 Nell'esempio di codice seguente viene illustrato il modello client consigliato usando un blocco try/catch e non l'istruzione `using`.  
  
 [!code-csharp[FaultContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
> [!NOTE]
> La verifica del valore della proprietà <xref:System.ServiceModel.ICommunicationObject.State%2A?displayProperty=nameWithType> è una race condition e non è consigliabile per determinare se riutilizzare o chiudere un canale.  
  
 I canali di datagramma non hanno mai esito negativo anche se si verificano eccezioni quando vengono chiusi. Inoltre, i client non duplex la cui autenticazione mediante conversazione protetta non riesce generano di norma un'eccezione <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>. Tuttavia, se il client duplex che usa una conversazione protetta non viene autenticato, riceve un'eccezione <xref:System.TimeoutException?displayProperty=nameWithType>.  
  
 Per informazioni più complete sull'utilizzo delle informazioni sugli errori a livello di applicazione, vedere [specifica e gestione di errori in contratti e servizi](../specifying-and-handling-faults-in-contracts-and-services.md). Le [eccezioni previste](../samples/expected-exceptions.md) descrivono le eccezioni previste e Mostra come gestirle. Per ulteriori informazioni su come gestire gli errori durante lo sviluppo di canali, vedere [gestione di eccezioni ed](../extending/handling-exceptions-and-faults.md)errori.  
  
### <a name="client-blocking-and-performance"></a>Blocco dei client e prestazioni  
 Quando un'applicazione chiama in modo sincrono un'operazione request-reply, il client si blocca fino a quando non viene ricevuto un valore restituito o non viene generata un'eccezione (ad esempio, <xref:System.TimeoutException?displayProperty=nameWithType>). Si tratta di un comportamento simile al comportamento locale. Quando un'applicazione richiama in modo sincrono un'operazione su un oggetto o un canale WCF, il client non viene restituito finché il livello del canale non è in grado di scrivere i dati nella rete o fino a quando non viene generata un'eccezione. Sebbene il modello di scambio di messaggi unidirezionale (specificato contrassegnando un'operazione con la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> impostata su `true`) possa aumentare la capacità di risposta di alcuni client, le operazioni unidirezionali possono anche creare blocchi, a seconda dell'associazione e dei messaggi già inviati. Le operazioni unidirezionali riguardano esclusivamente lo scambio di messaggi. Per ulteriori informazioni, vedere [Servizi unidirezionali](one-way-services.md).  
  
 I grandi blocchi di dati possono rallentare l'elaborazione dei client, indipendentemente dal modello di scambio di messaggi. Per comprendere come gestire questi problemi, vedere [dati di grandi dimensioni e flussi](large-data-and-streaming.md).  
  
 Se l'applicazione deve eseguire più operazioni durante il completamento di un'operazione, è necessario creare una coppia di metodi asincroni sull'interfaccia del contratto di servizio implementata dal client WCF. Il modo più semplice per eseguire questa operazione consiste nell'utilizzare l' `/async` opzione nello [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Per un esempio, vedere [procedura: chiamare operazioni del servizio in modo asincrono](how-to-call-wcf-service-operations-asynchronously.md).  
  
 Per altre informazioni su come aumentare le prestazioni del client, vedere [applicazioni client di livello intermedio](middle-tier-client-applications.md).  
  
### <a name="enabling-the-user-to-select-credentials-dynamically"></a>Abilitazione dell'utente alla selezione dinamica di credenziali  
 L'interfaccia <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> consente alle applicazioni di visualizzare un'interfaccia utente che consente all'utente di scegliere le credenziali con cui viene creato un canale prima dell'avvio dei timer di timeout.  
  
 Gli sviluppatori di applicazioni possono usare un'interfaccia <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> inserita in due modi. L'applicazione client può chiamare <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o una versione asincrona) prima di aprire il canale (approccio *esplicito* ) o chiamare la prima operazione (approccio *implicito* ).  
  
 Se si usa l'approccio implicito, l'applicazione deve chiamare la prima operazione su un'estensione <xref:System.ServiceModel.ClientBase%601> o <xref:System.ServiceModel.IClientChannel>. Se chiama un elemento diverso dalla prima operazione, viene generata un'eccezione.  
  
 Se si usa l'approccio esplicito, l'applicazione deve eseguire i passaggi seguenti nell'ordine rappresentato:  
  
1. Chiamare <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o una versione asincrona).  
  
2. Quando gli inizializzatori restituiscono un valore, chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.IClientChannel> o sull'oggetto <xref:System.ServiceModel.IClientChannel> restituito dalla proprietà <xref:System.ServiceModel.ClientBase%601.InnerChannel%2A?displayProperty=nameWithType>.  
  
3. Chiamare le operazioni.  
  
 È consigliabile che le applicazioni di alta qualità controllino il processo dell'interfaccia utente adottando l'approccio esplicito.  
  
 Le applicazioni che usano l'approccio implicito richiamano gli inizializzatori dell'interfaccia utente, ma se l'utente dell'applicazione non risponde entro il periodo di timeout di invio dell'associazione, viene generata un'eccezione quando viene restituita l'interfaccia utente.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi duplex](duplex-services.md)
- [Procedura: accedere a servizi con un contratto unidirezionale o request/reply](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [Procedura: accedere ai servizi con un contratto duplex](how-to-access-services-with-a-duplex-contract.md)
- [Procedura: accedere a WSE 3.0 Service](how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [Procedura: usare ChannelFactory](how-to-use-the-channelfactory.md)
- [Procedura: chiamare operazioni del servizio in modo asincrono](how-to-call-wcf-service-operations-asynchronously.md)
- [Applicazioni client di livello intermedio](middle-tier-client-applications.md)
