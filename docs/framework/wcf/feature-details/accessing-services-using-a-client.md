---
title: Accesso ai servizi tramite client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c8329832-bf66-4064-9034-bf39f153fc2d
ms.openlocfilehash: 03b37dae72be0ffa589159b2aedc2ac16e35139e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583207"
---
# <a name="accessing-services-using-a-client"></a>Accesso ai servizi tramite client
Le applicazioni client devono creare, configurare e usare oggetti client o canale WCF per comunicare con i servizi. Il [WCF Client Overview](../../../../docs/framework/wcf/wcf-client-overview.md) argomento fornisce una panoramica degli oggetti e passaggi coinvolti nella creazione di oggetti client e il canale di base e il relativo utilizzo.  
  
 In questo argomento vengono fornite informazioni dettagliate su alcuni dei problemi relativi ad applicazioni client e oggetti client e canale, che possono essere utili a seconda dello scenario.  
  
## <a name="overview"></a>Panoramica  
 In questo argomento vengono descritti il comportamento e i problemi relativi a:  
  
-   Durata di canali e sessioni.  
  
-   Gestione delle eccezioni.  
  
-   Problemi che causano blocchi.  
  
-   Inizializzazione interattiva dei canali.  
  
### <a name="channel-and-session-lifetimes"></a>Durata di canali e sessioni  
 Le applicazioni di Windows Communication Foundation (WCF) include due categorie di canali, datagramma e quelli con sessione.  
  
 Oggetto *datagramma* un canale in cui tutti i messaggi non sono correlati. Con un canale di datagramma, l'eventuale esito negativo di un'operazione di input o di output non ha di norma alcun effetto sulla successiva operazione ed è possibile riutilizzare lo stesso canale. Ne consegue che i canali di datagramma non hanno in genere esito negativo.  
  
 *Con sessione* canali, sono invece canali con una connessione a altro endpoint. I messaggi in una sessione su uno dei lati vengono sempre correlati alla stessa sessione sull'altro lato. Inoltre, perché una sessione possa essere considerata riuscita, entrambi i partecipanti a essa devono concordare sul fatto che i requisiti della conversazione siano stati soddisfatti. In caso contrario, il canale con sessione può avere esito negativo.  
  
 Aprire i client in modo esplicito o implicito chiamando la prima operazione.  
  
> [!NOTE]
>  Tentare di rilevare esplicitamente i canali con sessione in errore non è in genere utile, poiché il momento in cui si riceve la notifica dipende dall'implementazione della sessione. Poiché, ad esempio, la classe <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> (con la sessione affidabile disattivata) fa emergere la sessione della connessione TCP, se si è in ascolto dell'evento <xref:System.ServiceModel.ICommunicationObject.Faulted?displayProperty=nameWithType> sul servizio o sul client, è probabile che si riceva una notifica immediata in caso di errore di rete. Le sessioni affidabili (stabilite da associazioni in cui la classe <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> è attivata) sono però progettate per isolare i servizi da piccoli errori di rete. Se la sessione può essere ristabilita entro un periodo di tempo ragionevole, la stessa associazione, configurata per sessioni affidabili, potrebbe non generare errori fino a quando l'interruzione non dura per un periodo di tempo più lungo.  
  
 La maggior parte delle associazioni fornite dal sistema (che espongono canali al livello di applicazione) usa sessioni per impostazione predefinita, diversamente dall'associazione <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>. Per altre informazioni, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="the-proper-use-of-sessions"></a>Utilizzo corretto delle sessioni  
 Le sessioni offrono un modo per sapere se l'intero scambio di messaggi è completo e se entrambi i lati lo considerano riuscito. È consigliabile che un'applicazione chiamante apra il canale, lo utilizzi e lo chiuda all'interno di un unico blocco try. Se un canale di sessione è aperto, il metodo <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> viene chiamato una volta e la chiamata viene restituita correttamente, la sessione ha esito positivo. Per esito positivo si intende, in questo caso, che tutto il recapito garantisce che l'associazione specificata è stata soddisfatta e che l'altro lato non ha chiamato <xref:System.ServiceModel.ICommunicationObject.Abort%2A?displayProperty=nameWithType> sul canale prima di chiamare <xref:System.ServiceModel.ICommunicationObject.Close%2A>.  
  
 Nella sezione seguente viene fornito un esempio di tale approccio client.  
  
### <a name="handling-exceptions"></a>Gestione delle eccezioni  
 La gestione di eccezioni nelle applicazioni client è semplice. Se un canale viene aperto, usato e chiuso all'interno di un blocco try, la conversazione ha avuto esito positivo, a meno che non venga generata un'eccezione. In genere, se viene generata un'eccezione, la conversazione viene interrotta.  
  
> [!NOTE]
>  Usare la `using` istruzione (`Using` in Visual Basic) non è consigliata. poiché la fine dell'istruzione `using` può causare eccezioni che possono mascherare altre eccezioni che potrebbe essere necessario conoscere. Per altre informazioni, vedere [utilizzare Chiudi e Interrompi per rilasciare le risorse del client WCF](../../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md).  
  
 Nell'esempio di codice seguente viene illustrato il modello client consigliato usando un blocco try/catch e non l'istruzione `using`.  
  
 [!code-csharp[FaultContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
> [!NOTE]
>  La verifica del valore della proprietà <xref:System.ServiceModel.ICommunicationObject.State%2A?displayProperty=nameWithType> è una race condition e non è consigliabile per determinare se riutilizzare o chiudere un canale.  
  
 I canali di datagramma non hanno mai esito negativo anche se si verificano eccezioni quando vengono chiusi. Inoltre, i client non duplex la cui autenticazione mediante conversazione protetta non riesce generano di norma un'eccezione <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>. Tuttavia, se il client duplex che usa una conversazione protetta non viene autenticato, riceve un'eccezione <xref:System.TimeoutException?displayProperty=nameWithType>.  
  
 Per ulteriori informazioni sull'utilizzo con informazioni sull'errore a livello di applicazione, vedere [se si specifica e gestione degli errori in contratti e servizi](../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md). [Le eccezioni previste](../../../../docs/framework/wcf/samples/expected-exceptions.md) descrive le eccezioni previste e viene illustrato come gestirli. Per altre informazioni su come gestire gli errori durante lo sviluppo di canali, vedere [gestione delle eccezioni ed errori](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
### <a name="client-blocking-and-performance"></a>Blocco dei client e prestazioni  
 Quando un'applicazione chiama in modo sincrono un'operazione request-reply, il client si blocca fino a quando non viene ricevuto un valore restituito o non viene generata un'eccezione (ad esempio, <xref:System.TimeoutException?displayProperty=nameWithType>). Si tratta di un comportamento simile al comportamento locale. Quando un'applicazione richiama in modo sincrono un'operazione su un oggetto client WCF o un canale, il client non viene restituito fino a quando il livello del canale può scrivere i dati in rete o fino a quando non viene generata un'eccezione. Sebbene il modello di scambio di messaggi unidirezionale (specificato contrassegnando un'operazione con la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> impostata su `true`) possa aumentare la capacità di risposta di alcuni client, le operazioni unidirezionali possono anche creare blocchi, a seconda dell'associazione e dei messaggi già inviati. Le operazioni unidirezionali riguardano esclusivamente lo scambio di messaggi. Per altre informazioni, vedere [unidirezionale servizi](../../../../docs/framework/wcf/feature-details/one-way-services.md).  
  
 I grandi blocchi di dati possono rallentare l'elaborazione dei client, indipendentemente dal modello di scambio di messaggi. Per comprendere come gestire questi problemi, vedere [Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
 Se l'applicazione deve eseguire altre operazioni durante un'operazione viene completata, è consigliabile creare una coppia di metodi asincroni sull'interfaccia del contratto di servizio che implementa il client WCF. Il modo più semplice per eseguire questa operazione è usare il `/async` attivare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Per un esempio, vedere [Procedura: Chiamare operazioni del servizio in modo asincrono](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 Per altre informazioni sull'aumento delle prestazioni di client, vedere [le applicazioni Client di livello intermedio](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).  
  
### <a name="enabling-the-user-to-select-credentials-dynamically"></a>Abilitazione dell'utente alla selezione dinamica di credenziali  
 L'interfaccia <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> consente alle applicazioni di visualizzare un'interfaccia utente che consente all'utente di scegliere le credenziali con cui viene creato un canale prima dell'avvio dei timer di timeout.  
  
 Gli sviluppatori di applicazioni possono usare un'interfaccia <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> inserita in due modi. L'applicazione client può chiamare <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> oppure <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o una versione asincrona) prima dell'apertura del canale (il *esplicita* approccio) o chiamare la prima operazione (il *implicita*approccio).  
  
 Se si usa l'approccio implicito, l'applicazione deve chiamare la prima operazione su un'estensione <xref:System.ServiceModel.ClientBase%601> o <xref:System.ServiceModel.IClientChannel>. Se chiama un elemento diverso dalla prima operazione, viene generata un'eccezione.  
  
 Se si usa l'approccio esplicito, l'applicazione deve eseguire i passaggi seguenti nell'ordine rappresentato:  
  
1.  Chiamare <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o una versione asincrona).  
  
2.  Quando gli inizializzatori restituiscono un valore, chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.IClientChannel> o sull'oggetto <xref:System.ServiceModel.IClientChannel> restituito dalla proprietà <xref:System.ServiceModel.ClientBase%601.InnerChannel%2A?displayProperty=nameWithType>.  
  
3.  Chiamare le operazioni.  
  
 È consigliabile che le applicazioni di alta qualità controllino il processo dell'interfaccia utente adottando l'approccio esplicito.  
  
 Le applicazioni che usano l'approccio implicito richiamano gli inizializzatori dell'interfaccia utente, ma se l'utente dell'applicazione non risponde entro il periodo di timeout di invio dell'associazione, viene generata un'eccezione quando viene restituita l'interfaccia utente.  
  
## <a name="see-also"></a>Vedere anche
- [Servizi duplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)
- [Procedura: Accedere ai servizi con un contratto unidirezionale e i contratti Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [Procedura: Servizi di accesso con un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Procedura: Accedere a WSE 3.0 Service](../../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [Procedura: Usare ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
- [Procedura: Chiamare operazioni del servizio in modo asincrono](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [Applicazioni client di livello intermedio](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md)
