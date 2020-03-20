---
title: Raggruppamento di messaggi in coda in una sessione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 231310e5c427f507141e3c144cb02b8e848d4fbf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185162"
---
# <a name="grouping-queued-messages-in-a-session"></a>Raggruppamento di messaggi in coda in una sessione
Windows Communication Foundation (WCF) fornisce una sessione che consente di raggruppare un set di messaggi correlati per l'elaborazione da una singola applicazione ricevente. I messaggi appartenenti a una sessione devono appartenere alla stessa transazione. Poiché tutti i messaggi appartengono alla stessa transazione, se l'elaborazione di un messaggio non riesce viene eseguito il rollback dell'intera sessione. Le sessioni presentano comportamenti simili relativamente alle code di messaggi non recapitabili e alle code di messaggi non elaborabili. La proprietà di durata (TTL, Time To Live) impostata in un'associazione in coda configurata per una determinata sessione viene applicata all'intera sessione. Se allo scadere del TTL è stata inviata solo una parte dei messaggi, l'intera sessione viene inserita nella coda di messaggi non recapitabili. Analogamente, quando risulta impossibile inviare a un'applicazione alcuni messaggi di una sessione contenuti nella coda dell'applicazione, l'intera sessione viene inserita nella coda di messaggi non elaborabili (se disponibile).  
  
## <a name="message-grouping-example"></a>Esempio di raggruppamento di messaggi  
 Un esempio in cui il raggruppamento dei messaggi è utile è l'implementazione di un'applicazione di elaborazione degli ordini come servizio WCF. Si supponga ad esempio che un client invii a questa applicazione un ordine contenente alcuni elementi. Per ogni elemento il client effettua una chiamata al servizio. Ciò comporta l'invio di un messaggio a parte per ogni elemento. È possibile che il server A riceva il primo elemento e il server B riceva il secondo elemento. Ogni volta che viene aggiunto un elemento, il server che lo sta elaborando deve individuare l'ordine associato e quindi aggiungervi tale elemento. Ciò risulta particolarmente inefficiente. Gli stessi problemi di inefficienza si presentano anche utilizzando un unico server che gestisce tutte le richieste. Infatti, tale server deve tenere traccia di tutti gli ordini correntemente in elaborazione e determinare a quale di essi appartiene il nuovo elemento. Il raggruppamento di tutte le richieste relative a un determinato ordine consente di semplificare notevolmente l'implementazione dell'applicazione descritta. L'applicazione client invia in una sessione tutti gli elementi relativi a un determinato ordine. Pertanto, quando il servizio elabora l'ordine, elabora l'intera sessione in un'unica operazione. \  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>Per configurare l'utilizzo di sessioni in un contratto di servizio  
  
1. Definire un contratto di servizio che richieda una sessione. Eseguire questa <xref:System.ServiceModel.ServiceContractAttribute> operazione con l'attributo specificando:  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. Poiché questi metodi non restituiscono alcun dato, contrassegnare le operazioni del contratto come unidirezionali. Questa operazione viene <xref:System.ServiceModel.OperationContractAttribute> eseguita con l'attributo specificando:  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. Implementare il contratto di servizio e specificare la modalità <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode><xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>. Ciò comporta la creazione di un'unica istanza del servizio per ogni sessione.  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. Per ogni operazione del servizio è necessario specificare una transazione. A tale scopo, utilizzare l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>. L'operazione che completa la transazione deve inoltre impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> su `true`.  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. Configurare un endpoint che utilizza l'associazione `NetMsmqBinding` fornita dal sistema.  
  
6. Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>. Tale coda può anche essere creata tramite il sistema di accodamento dei messaggi (MSMQ) o la console MMC. In tal caso, creare una coda transazionale.  
  
7. Creare un host del servizio mediante la classe <xref:System.ServiceModel.ServiceHost>.  
  
8. Aprire l'host del servizio per rendere disponibile il servizio.  
  
9. Chiudere l'host del servizio.  
  
#### <a name="to-set-up-a-client"></a>Per configurare un client  
  
1. Creare un ambito di transazione per scrivere nella coda transazionale.  
  
2. Creare il client WCF utilizzando lo strumento [ServiceModel Metadata Utility Tool (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
  
3. Inviare l'ordine.  
  
4. Chiudere il client WCF.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene riportato il codice del servizio `IProcessOrder` e di un client che utilizza tale servizio. Viene illustrato come WCF utilizza le sessioni in coda per fornire il comportamento di raggruppamento.  
  
### <a name="code-for-the-service"></a>Codice del servizio  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a>Codice del client  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a>Vedere anche

- [Sessioni e code](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [Panoramica delle code](../../../../docs/framework/wcf/feature-details/queues-overview.md)
