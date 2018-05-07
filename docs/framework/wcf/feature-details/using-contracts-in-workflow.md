---
title: Uso di contratti nel flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: 1772c61147bb8a96f3f78b4226a1d341df3eb9d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-contracts-in-workflow"></a>Uso di contratti nel flusso di lavoro
In caso di implementazione di un servizio, viene definito un numero di contratti che descrivono il servizio e i dati inviati e ricevuti. I dati vengono rappresentati come contratti dati e contratti di messaggio; servizi WCF e del flusso di lavoro utilizzano definizioni del contratto dati contratto e messaggio come parte delle descrizioni del servizio. Il servizio stesso espone metadati (nel formato WSDL) per descrivere le operazioni del servizio. In WCF i contratti di servizio e i contratti di operazione definiscono il servizio e le operazioni supportate. Tuttavia, in un servizio flusso di lavoro, questi contratti costituiscono parte del processo aziendale stesso e vengono esposti nei metadati da un processo denominato inferenza del contratto.  
  
## <a name="contract-inference"></a>Inferenza del contratto  
 Se un servizio flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene esaminata la definizione del flusso di lavoro e viene generato un contratto in base al set delle attività di messaggistica rilevato nel flusso di lavoro. In particolare vengono utilizzate le attività e le proprietà indicate di seguito per generare il contratto:  
  
 Attività <xref:System.ServiceModel.Activities.Receive>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 Attività <xref:System.ServiceModel.Activities.SendReply>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 Attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
 Il risultato finale di inferenza del contratto rappresenta una descrizione del servizio utilizzando le stesse strutture dei dati del servizio WCF e dei contratti dell'operazione. Queste informazioni vengono quindi usate per esporre WSDL per il servizio flusso di lavoro.  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Attività di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [Procedura: Creare un servizio flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
