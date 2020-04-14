---
title: Specifica del comportamento in fase di esecuzione del servizio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5c5450ea-6af1-4b75-a267-613d0ac54707
ms.openlocfilehash: 246f16cee85633499a6a1c200e608ee7bccf133c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243102"
---
# <a name="specifying-service-run-time-behavior"></a>Specifica del comportamento in fase di esecuzione del servizio
Dopo aver definito un contratto di servizio ([Designing Service Contracts](designing-service-contracts.md)) e implementato tale contratto ([Implementing Service Contracts](implementing-service-contracts.md)), è possibile configurare il comportamento operativo del runtime del servizio. In questo argomento vengono illustrati i comportamenti dell'operazione e del servizio forniti dal sistema e viene descritto dove trovare ulteriori informazioni per creare nuovi comportamenti. Mentre alcuni comportamenti vengono applicati come attributi, molti vengono applicati utilizzando un file di configurazione dell'applicazione o a livello di codice. Per ulteriori informazioni sulla configurazione dell'applicazione di servizio, vedere [Configurazione dei servizi](configuring-services.md).  
  
## <a name="overview"></a>Panoramica  
 Il contratto definisce gli input, gli output, i tipi di dati e le funzionalità di un servizio di quel tipo. L'implementazione di un contratto di servizio crea una classe che, in caso di configurazione con un'associazione in un indirizzo, adempie al contratto che implementa. Il client conosce le informazioni contrattuali, sull'associazione e sull'indirizzo, senza le quali non potrebbe utilizzare il servizio.  
  
 Le specifiche dell'operazione, ad esempio i problemi di threading o la gestione delle istanze, sono tuttavia opache ai client. Dopo aver implementato il contratto di servizio, è possibile configurare numerose caratteristiche dell'operazione utilizzando i *comportamenti*. I comportamenti sono oggetti che modificano il runtime di Windows Communication Foundation (WCF) impostando una proprietà di runtime o inserendo un tipo di personalizzazione nel runtime. Per ulteriori informazioni sulla modifica del runtime mediante la creazione di comportamenti definiti dall'utente, vedere Estensione di [ServiceHost e del](./extending/extending-servicehost-and-the-service-model-layer.md)livello del modello di servizio .  
  
 Gli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> e <xref:System.ServiceModel.OperationBehaviorAttribute?displayProperty=nameWithType> sono i comportamenti più utili ed espongono le funzionalità dell'operazione richieste più comunemente. Essendo degli attributi, vengono applicati all'implementazione del servizio o dell'operazione. Altri comportamenti, ad esempio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior?displayProperty=nameWithType>, vengono in genere applicati utilizzando un file di configurazione dell'applicazione, anche se è possibile utilizzarli a livello di programmazione.  
  
 In questo argomento viene <xref:System.ServiceModel.ServiceBehaviorAttribute> <xref:System.ServiceModel.OperationBehaviorAttribute> fornita una panoramica degli attributi e , vengono descritti i vari ambiti in cui i comportamenti possono operare e viene fornita una breve descrizione di molti dei comportamenti forniti dal sistema nei vari ambiti che possono essere di interesse per gli sviluppatori WCF.  
  
## <a name="servicebehaviorattribute-and-operationbehaviorattribute"></a>ServiceBehaviorAttribute e OperationBehaviorAttribute  
 I comportamenti più importanti sono gli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute> che è possibile utilizzare per controllare:  
  
- Durate delle istanze  
  
- Supporto di sincronizzazione e concorrenza  
  
- Comportamento di configurazione  
  
- Comportamento della transazione  
  
- Comportamento della serializzazione  
  
- Trasformazione dei metadati  
  
- Durata della sessione  
  
- Filtraggio dell'indirizzo ed elaborazione dell'intestazione  
  
- Rappresentazione  
  
- Per utilizzare questi attributi, contrassegnare l'implementazione del servizio o dell'operazione con l'attributo appropriato per quell'ambito e impostare le proprietà. Nell'esempio di codice seguente, ad esempio, viene illustrata un'implementazione dell'operazione che utilizza la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A?displayProperty=nameWithType> per richiedere che i chiamanti di questa operazione supportino la rappresentazione.  
  
 [!code-csharp[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/operationbehaviorattribute_impersonation/cs/services.cs#1)]
 [!code-vb[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationbehaviorattribute_impersonation/vb/services.vb#1)]  
  
 Molte delle proprietà richiedono supporto aggiuntivo dall'associazione. Un'operazione che richiede una transazione dal client, ad esempio, deve essere configurata in modo che utilizzi un'associazione che supporta transazioni propagate.  
  
### <a name="well-known-singleton-services"></a>Servizi Singleton noti  
 È possibile utilizzare gli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute> per controllare determinate durate, sia di <xref:System.ServiceModel.InstanceContext> che degli oggetti servizio che implementano le operazioni.  
  
 La proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> , ad esempio, consente di controllare la frequenza di rilascio di <xref:System.ServiceModel.InstanceContext> , mentre le proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> consentono di controllare quando l'oggetto servizio viene rilasciato.  
  
 È tuttavia possibile creare un oggetto servizio e quindi creare l'host del servizio tramite quell'oggetto. A tale scopo, è necessario impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.InstanceContextMode.Single> , in caso contrario verrà generata un'eccezione quando l'host del servizio viene aperto.  
  
 Utilizzare il costruttore <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29> per creare tale servizio. Fornisce un'alternativa all'implementazione di un'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> personalizzata quando si desidera fornire un'istanza specifica dell'oggetto utilizzabile da un servizio singleton. È possibile utilizzare questo overload quando il tipo di implementazione del servizio è difficile da costruire (ad esempio, se non implementa un costruttore pubblico senza parametri).
  
 Si noti che quando un oggetto viene fornito a questo costruttore, alcune funzionalità correlate al comportamento di creazione di istanze di Windows Communication Foundation (WCF) funzionano in modo diverso. La chiamata, ad esempio, di <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> non ha effetto quando viene fornita l'istanza di un oggetto noto. Analogamente, qualsiasi altro meccanismo di rilascio delle istanze viene ignorato. La classe <xref:System.ServiceModel.ServiceHost> si comporta sempre come se la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> fosse impostata su <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> per tutte le operazioni.  
  
## <a name="other-service-endpoint-contract-and-operation-behaviors"></a>Altri comportamenti del servizio, dell'endpoint, del contratto e dell'operazione  
 I comportamenti del servizio, ad esempio l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> , agiscono su un servizio intero. Se, ad esempio, si imposta la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> , è necessario gestire i problemi di sincronizzazione dei thread all'interno di ogni operazione in quel servizio. I comportamenti dell'endpoint operano all'interno di un endpoint. Molti dei comportamenti dell'endpoint forniti dal sistema interessano la funzionalità client. I comportamenti del contratto operano a livello di contratto e i comportamenti dell'operazione modificano il recapito dell'operazione.  
  
 Molti di questi comportamenti vengono implementati sugli attributi e vengono utilizzati come si utilizzano gli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute> , applicandoli alla classe di servizio appropriata o all'implementazione dell'operazione. Altri comportamenti, ad esempio gli oggetti <xref:System.ServiceModel.Description.ServiceMetadataBehavior> o <xref:System.ServiceModel.Description.ServiceDebugBehavior> , vengono in genere applicati utilizzando un file di configurazione dell'applicazione, sebbene sia possibile utilizzarli anche a livello di programmazione.  
  
 La pubblicazione di metadati, ad esempio, viene configurata utilizzando l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> . Nel file seguente di configurazione dell'applicazione viene illustrato l'utilizzo più comune.  
  
 [!code-xml[ServiceMetadataBehavior#1](../../../samples/snippets/csharp/VS_Snippets_CFX/servicemetadatabehavior/cs/hostapplication.exe.config#1)]  
  
 Nelle sezioni seguenti vengono descritti molti dei comportamenti più utili forniti dal sistema e che possono essere utilizzati per modificare il recapito runtime del servizio o del client. Per informazioni su come utilizzare ognuno di essi, vedere l'argomento di riferimento.  
  
### <a name="service-behaviors"></a>Comportamenti del servizio  
 I comportamenti seguenti operano sui servizi.  
  
- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>. Applicato a un servizio WCF per indicare se tale servizio può essere eseguito in modalità compatibilità ASP.NET.Applied to a WCF service to indicate whether that service can be run in ASP.NET Compatibility Mode.  
  
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Controlla come il servizio autorizza le richieste del client.  
  
- <xref:System.ServiceModel.Description.ServiceCredentials>. Configura una credenziale del servizio. Utilizzare questa classe per specificare la credenziale per il servizio, ad esempio un certificato X.509.  
  
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>. Abilita le funzionalità di debug e informazioni della Guida per un servizio WCF.  
  
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. Controlla la pubblicazione dei metadati del servizio e delle informazioni associate.  
  
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>. Specifica il comportamento di controllo degli eventi di sicurezza.  
  
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>. Configura le impostazioni di velocità runtime che consentono di ottimizzare le prestazioni del servizio.  
  
### <a name="endpoint-behaviors"></a>Comportamenti dell'endpoint  
 I comportamenti seguenti operano sugli endpoint. Molti di questi comportamenti sono utilizzati in applicazioni client.  
  
- <xref:System.ServiceModel.CallbackBehaviorAttribute>. Configura l'implementazione di un servizio di callback in un'applicazione client duplex.  
  
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>. Abilita il debug del servizio per un oggetto callback WCF.  
  
- <xref:System.ServiceModel.Description.ClientCredentials>. Consente all'utente di configurare le credenziali client e del servizio, nonché le impostazioni di autenticazione delle credenziali del servizio da utilizzare nel client.  
  
- <xref:System.ServiceModel.Description.ClientViaBehavior>. Utilizzato dai client per specificare l'URI (Uniform Resource Identifier) per il quale deve essere creato il canale di trasporto.  
  
- <xref:System.ServiceModel.Description.MustUnderstandBehavior>. Indica a WCF di `MustUnderstand` disabilitare l'elaborazione.  
  
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>. Indica al runtime di utilizzare un processo di ricezione sincrono per i canali.  
  
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Ottimizza le operazioni di ricezione per i trasporti che supportano ricezioni transazionali.  
  
### <a name="contract-behaviors"></a>Comportamenti del contratto  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>. Specifica i requisiti della funzionalità che le associazioni devono fornire all'implementazione del servizio o del client.  
  
### <a name="operation-behaviors"></a>Comportamenti dell'operazione  
 I comportamenti dell'operazione seguenti specificano i controlli di serializzazione e di transazione per le operazioni.  
  
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. Rappresenta il comportamento runtime di <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>. Controlla il comportamento runtime di `XmlSerializer` e lo associa a un'operazione.  
  
- <xref:System.ServiceModel.TransactionFlowAttribute>. Specifica il livello al quale un'operazione del servizio accetta un'intestazione di transazione.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi](configuring-services.md)
- [Procedura: Controllare le istanze del servizio](./feature-details/how-to-control-service-instancing.md)
