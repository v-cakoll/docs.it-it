---
title: Uso di sessioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: sessions [WCF]
ms.assetid: 864ba12f-3331-4359-a359-6d6d387f1035
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82fab5b5d7c702bc9f5e595572b8eba821159cd7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-sessions"></a>Uso di sessioni
Nelle applicazioni [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] una *sessione* correla un gruppo di messaggi in una conversazione. Le sessioni[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono differenti dall'oggetto sessione disponibile nelle applicazioni [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] , supportano comportamenti diversi e sono controllate in modi diversi. In questo argomento vengono descritte le funzionalità che vengono attivate dalle sessioni nelle applicazioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e le relative modalità di utilizzo.  
  
## <a name="sessions-in-windows-communication-foundation-applications"></a>Sessioni nelle applicazioni Windows Communication Foundation  
 Quando un contratto di servizio specifica che è necessaria una sessione, significa che tutte le chiamate, ovvero gli scambi di messaggi sottostanti che supportano le chiamate, devono essere parte della stessa conversazione. Se un contratto consente sessioni ma non ne richiede, i client possono connettersi e possono stabilire o meno una sessione. Se, al termine della sessione, un messaggio viene inviato sullo stesso canale basato sulla sessione, viene generata un'eccezione.  
  
 Le principali caratteristiche delle sessioni[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono le seguenti:  
  
-   Vengono avviate e terminate esplicitamente dall'applicazione chiamante (client WCF).  
  
-   I messaggi recapitati durante una sessione vengono elaborati nell'ordine in cui vengono ricevuti.  
  
-   Le sessioni consentono di correlare un gruppo di messaggi in una conversazione. Sono possibili diversi tipi di correlazione. Un canale basato sulla sessione, ad esempio, è in grado di correlare messaggi basati su una connessione di rete condivisa mentre un altro canale basato sulla sessione è in grado di correlare messaggi basati su un tag condiviso nel corpo del messaggio. Le funzionalità che possono derivare dalla sessione dipendono dalla natura della correlazione.  
  
-   Non esiste alcun archivio dati generale associato a una sessione [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
 Se si ha familiarità con la classe <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> in applicazioni [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e con la funzionalità fornita, è possibile notare le differenze seguenti tra quel tipo di sessioni e le sessioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Le sessioni[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] sono sempre avviate dal server.  
  
-   Le sessioni[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] sono implicitamente non ordinate.  
  
-   Le sessioni[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] forniscono un meccanismo di archiviazione dati generale tramite richieste.  
  
 In questo argomento vengono descritti gli argomenti seguenti:  
  
-   Il comportamento di esecuzione predefinito quando si utilizzano associazioni basate su sessione nel livello del modello di servizio.  
  
-   I tipi di funzionalità forniti dalle associazioni fornite dal sistema, basate sulla sessione [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
-   Come creare un contratto che dichiara un requisito della sessione.  
  
-   Come comprendere e controllare la creazione e chiusura della sessione e la relazione della sessione all'istanza del servizio.  
  
## <a name="default-execution-behavior-using-sessions"></a>Comportamento di esecuzione predefinito utilizzando le sessioni  
 Un'associazione che tenta di avviare una sessione è chiamata un'associazione *basata sulla sessione* . Nei contratti di servizio viene specificata la richiesta, permesso o rifiuto di associazioni basate sulla sessione tramite l'impostazione della proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> sull'interfaccia del contratto di servizio (o classe) su uno dei valori di enumerazione <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>. Per impostazione predefinita, il valore di questa proprietà è <xref:System.ServiceModel.SessionMode.Allowed>, che significa che se un client utilizza un'associazione basata sulla sessione con un'implementazione di servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , il servizio stabilisce e utilizza la sessione fornita.  
  
 Quando un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] accetta una sessione client, per impostazione predefinita vengono attivate le funzionalità seguenti:  
  
1.  Tutte le chiamate tra un oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono gestite dalla stessa istanza del servizio.  
  
2.  Diverse associazioni basate sulla sessione forniscono caratteristiche aggiuntive.  
  
## <a name="system-provided-session-types"></a>Tipi di sessione forniti dal sistema  
 Un'associazione basata sulla sessione supporta l'associazione predefinita di un'istanza del servizio con una determinata sessione. Tuttavia, associazioni basate sulla sessione diverse supportano funzionalità diverse oltre a consentire il controllo delle istanze basate sulla sessione descritto in precedenza.  
  
 In[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] vengono forniti i tipi seguenti di comportamento dell'applicazione basato sulla sessione:  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType> supporta sessioni basate sulla protezione nelle quali entrambe le parti della comunicazione hanno concordato una conversazione sicura specifica. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Protezione dei servizi](../../../docs/framework/wcf/securing-services.md). Ad esempio, l'associazione <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>, che contiene il supporto sia per le sessioni di sicurezza sia per le sessioni affidabili, per impostazione predefinita utilizza solo una sessione protetta che esegue la crittografia e la firma digitale dei messaggi.  
  
-   L'associazione <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> supporta le sessioni TCP/IP per garantire che tutti i messaggi siano correlati in base alla connessione a livello di socket.  
  
-   L'elemento <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>, che implementa la specifica WS-ReliableMessaging, supporta le sessioni affidabili in cui i messaggi possono essere configurati per essere recapitati nell'ordine ed esattamente una volta, in modo da garantire che i messaggi siano ricevuti anche quando durante la conversazione i messaggi passano per più nodi. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Le sessioni affidabili](../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
-   L'associazione <xref:System.ServiceModel.NetMsmqBinding?displayProperty=nameWithType> fornisce sessioni di datagramma di MSMQ. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Code in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
 L'impostazione della proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> non specifica il tipo di sessione richiesto dal contratto ma soltanto che il contratto ne richiede una.  
  
## <a name="creating-a-contract-that-requires-a-session"></a>Creazione di un contratto che richiede una sessione.  
 La creazione di un contratto che richiede una sessione dichiara che il gruppo di operazioni che vengono dichiarate dal contratto di servizio devono essere eseguite tutte all'interno della stessa sessione e che i messaggi devono essere recapitati nell'ordine. Per asserire il livello di supporto della sessione richiesto da un contratto di servizio, impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> sull'interfaccia o classe del contratto di servizio sul valore dell'enumerazione <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> da specificare se il contratto:  
  
-   Richiede una sessione.  
  
-   Consente a un client di stabilire una sessione.  
  
-   Proibisce una sessione.  
  
 L'impostazione della proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> non specifica, tuttavia, il tipo di comportamento basato sulla sessione richiesto dal contratto. Indica a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] di confermare in fase di esecuzione che l'associazione configurata, la quale crea il canale di comunicazione, per il servizio è più o meno in grado di stabilire una sessione quando viene implementato un servizio. Nuovamente, l'associazione è in grado di soddisfare tale requisito con qualsiasi tipo di comportamento basato sulla sessione che sceglie: protezione, trasporto, affidabile o una combinazione di questi. Il comportamento esatto dipende dal valore <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> selezionato. Se l'associazione configurata del servizio non è conforme al valore di <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A>, viene generata un'eccezione. Si dice che associazioni e i canali che creano quelle sessioni del supporto siano basato sulla sessione.  
  
 Il contratto di servizio seguente specifica che tutte le operazioni in `ICalculatorSession` devono essere scambiate all'interno di una sessione. Nessuna delle operazioni restituisce un valore al chiamante eccetto il metodo `Equals` . Tuttavia, il metodo `Equals` non prende parametri e, pertanto, può restituire solo un valore diverso da zero all'interno di una sessione nella quale i dati sono già stati passati alle altre operazioni. Per un funzionamento corretto, questo contratto necessita di una sessione. Senza una sessione associata a un client specifico, l'istanza del servizio non ha modo di conoscere i dati precedenti inviati da questo client.  
  
 [!code-csharp[S_Service_Session#1](../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
 Se un servizio autorizza a una sessione, allora ne viene stabilita e utilizzata se il client ne avvia una; in caso contrario, non viene stabilita alcuna sessione.  
  
## <a name="sessions-and-service-instances"></a>Sessioni e istanze del servizio  
 Se si utilizza il comportamento di istanza predefinito in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], tutte le chiamate tra un oggetto client di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] vengono gestite dalla stessa istanza del servizio. Di conseguenza, a livello di applicazione, è possibile pensare a una sessione come attivazione di un comportamento dell'applicazione simile al comportamento della chiamata locale. Ad esempio, quando si crea un oggetto locale:  
  
-   Viene chiamato un costruttore.  
  
-   Tutte le chiamate successive eseguite al riferimento dell'oggetto client di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono elaborate dalla stessa istanza dell'oggetto.  
  
-   Viene chiamato un distruttore quando il riferimento dell'oggetto viene distrutto.  
  
 Le sessioni attivano un comportamento simile tra client e servizi finché viene utilizzato il comportamento di istanza di servizio predefinito. Se un contratto di servizio richiede o supporta le sessioni, è possibile contrassegnare una o più operazioni del contratto come di avvio o chiusura di una sessione impostando le proprietà <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A> e <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A> .  
  
 *Operazioni di avvio* sono quelle che devono essere chiamate come prima operazione di una nuova sessione. Le operazioni non di avvio possono essere chiamate solo dopo che è stata chiamata almeno un'operazione di avvio. È pertanto possibile creare qualche tipo di costruttore di sessione per il servizio dichiarando operazioni di avvio progettate per ricevere dai client input appropriato per l'inizio dell'istanza del servizio. Tuttavia, lo stato è associato alla sessione e non all'oggetto servizio.  
  
 *Operazioni di chiusura*, al contrario, sono quelle che devono essere chiamate come ultimo messaggio in una sessione esistente. Nel caso predefinito, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ricicla l'oggetto servizio e il relativo contesto dopo la chiusura della sessione con cui è associato il servizio. È possibile, pertanto, creare un tipo di distruttore dichiarando operazioni di chiusura progettate per eseguire una funzione appropriata alla fine dell'istanza del servizio.  
  
> [!NOTE]
>  Anche se il comportamento predefinito reca qualche somiglianza con costruttori e distruttori locali, si tratta solo di una somiglianza. Qualsiasi operazione di servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] può essere un'operazione di avvio o chiusura, o entrambe allo stesso tempo. Inoltre, nel caso predefinito, le operazioni di avvio possono essere chiamate qualsiasi numero di volte e in qualsiasi ordine; dopo che la sessione è stata stabilita e associata a un'istanza non vengono create altre sessioni a meno che non venga controllata in modo esplicito la durata dell'istanza del servizio (modificando l'oggetto <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>). Infine, lo stato viene associato alla sessione e non all'oggetto servizio.  
  
 Ad esempio, il contratto `ICalculatorSession` utilizzato nell'esempio precedente richiede che l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] chiami innanzitutto l'operazione `Clear` prima di qualsiasi altra e che la sessione con questo oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] debba terminare quando viene chiamata l'operazione `Equals` . Nell'esempio di codice seguente è illustrato un contratto che applica questi requisiti. `Clear` deve essere chiamato per primo per avviare una sessione e tale sessione termina quando viene chiamato `Equals` .  
  
 [!code-csharp[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.isinitiatingisterminating/cs/service.cs#1)]
 [!code-vb[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.isinitiatingisterminating/vb/service.vb#1)]  
  
 I servizi non avviano sessioni con i client. Nelle applicazioni client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , esiste una relazione diretta tra la durata del canale basato sulla sessione e la durata della sessione stessa. In tal senso, i client creano nuove sessioni creando nuovi canali basati sulla sessione e chiudono le sessioni esistenti chiudendo normalmente i canali basati sulla sessione. Un client avvia una sessione con un endpoint del servizio chiamando uno degli elementi seguenti:  
  
-   <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> nel canale restituito da una chiamata a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>.  
  
-   <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>nel [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] oggetto client generato dal [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
-   Un'operazione di avvio su un tipo di oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (per impostazione predefinita, tutte le operazioni sono di avvio). Quando la prima operazione viene chiamata, l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] apre automaticamente il canale e avvia una sessione.  
  
 In genere, un client termina una sessione con un endpoint del servizio chiamando uno degli elementi seguenti:  
  
-   <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> nel canale restituito da una chiamata a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>.  
  
-   <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType> nell'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] generato da Svcutil.exe.  
  
-   Un'operazione di chiusura su un tipo di oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (per impostazione predefinita, nessuna operazione è di chiusura; il contratto deve specificare in modo esplicito un'operazione di chiusura). Quando la prima operazione viene chiamata, l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] apre automaticamente il canale e avvia una sessione.  
  
 Per alcuni esempi, vedere [How to: Create a Service That Requires Sessions](../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md) , nonché [Default Service Behavior](../../../docs/framework/wcf/samples/default-service-behavior.md) e [Instancing](../../../docs/framework/wcf/samples/instancing.md) .  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]i client e le sessioni, vedere [accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Sessioni che interagiscono con impostazioni InstanceContext  
 Esiste un'interazione tra l'enumerazione <xref:System.ServiceModel.SessionMode> in un contratto e la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType>, che consente di controllare l'associazione tra canali e oggetti servizio specifici. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Sessioni, istanze e concorrenza](../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md).  
  
### <a name="sharing-instancecontext-objects"></a>Condivisione di oggetti InstanceContext  
 È inoltre possibile controllare l'associazione tra canali basati sulla sessione o chiamate con sessione e oggetti <xref:System.ServiceModel.InstanceContext> eseguendo quell'associazione. Per un esempio completo, vedere [InstanceContextSharing](http://msdn.microsoft.com/en-us/4a6a46d7-b7d7-4bb5-a0dd-03ffa3cbc230).  
  
## <a name="sessions-and-streaming"></a>Sessioni e flusso  
 Quando è necessario trasferire una notevole quantità di dati, la modalità del trasferimento in flusso di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è un'alternativa possibile al comportamento predefinito di memorizzazione nel buffer ed elaborazione in memoria dei messaggi per intero. È possibile ricevere un comportamento imprevisto quando viene eseguito il flusso delle chiamate con un'associazione basata sulla sessione. Tutte le chiamate del flusso sono eseguite tramite un solo canale (il canale del datagramma) che non supporta sessioni anche se l'associazione utilizzata è configurata per utilizzare sessioni. Se più client effettuano un flusso di chiamate allo stesso oggetto servizio con un'associazione basata sulla sessione, la modalità di concorrenza dell'oggetto servizio è impostata su Single e la modalità di contesto dell'istanza è impostata su `PerSession`, tutte le chiamate devono transitare attraverso il canale del datagramma, pertanto viene elaborata una sola chiamata alla volta. Uno o più client possono quindi scadere. È possibile risolvere questo problema impostando `InstanceContextMode` dell'oggetto servizio su `PerCall` o Concurrency su Multiple.  
  
> [!NOTE]
>  In questo caso, MaxConcurrentSessions non produce alcun effetto perché è disponibile una sola "sessione".  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A>
