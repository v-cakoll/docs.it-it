---
title: Uso di contratti nel flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: def100f9483ea9ac8bf1aa3285d76edccffb030a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595011"
---
# <a name="using-contracts-in-workflow"></a>Uso di contratti nel flusso di lavoro
In caso di implementazione di un servizio, viene definito un numero di contratti che descrivono il servizio e i dati inviati e ricevuti. I dati sono rappresentati come contratti dati e contratti di messaggio; i servizi WCF e Workflow utilizzano le definizioni del contratto dati e del contratto di messaggio come parte delle descrizioni dei servizi. Il servizio stesso espone metadati (nel formato WSDL) per descrivere le operazioni del servizio. In WCF i contratti di servizio e i contratti di operazione definiscono il servizio e le operazioni supportate. Tuttavia, in un servizio flusso di lavoro, questi contratti costituiscono parte del processo aziendale stesso e vengono esposti nei metadati da un processo denominato inferenza del contratto.  
  
## <a name="contract-inference"></a>Inferenza del contratto  
 Se un servizio flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene esaminata la definizione del flusso di lavoro e viene generato un contratto in base al set delle attività di messaggistica rilevato nel flusso di lavoro. In particolare vengono utilizzate le attività e le proprietà indicate di seguito per generare il contratto:  
  
 <xref:System.ServiceModel.Activities.Receive> Attività  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <xref:System.ServiceModel.Activities.SendReply> Attività  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> Attività  
  
 Il risultato finale di inferenza del contratto rappresenta una descrizione del servizio utilizzando le stesse strutture dei dati del servizio WCF e dei contratti dell'operazione. Queste informazioni vengono quindi usate per esporre WSDL per il servizio flusso di lavoro.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](workflow-services.md)
- [Attività di messaggistica](messaging-activities.md)
- [Procedura: creare un servizio flusso di lavoro con attività di messaggistica](how-to-create-a-workflow-service-with-messaging-activities.md)
- [Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
