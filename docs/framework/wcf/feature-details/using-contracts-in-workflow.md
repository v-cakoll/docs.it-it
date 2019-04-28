---
title: Uso di contratti nel flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: dd35766011c412acc937eed75d523a0574f6b9cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918541"
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="b6a00-102">Uso di contratti nel flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6a00-102">Using Contracts in Workflow</span></span>
<span data-ttu-id="b6a00-103">In caso di implementazione di un servizio, viene definito un numero di contratti che descrivono il servizio e i dati inviati e ricevuti.</span><span class="sxs-lookup"><span data-stu-id="b6a00-103">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="b6a00-104">I dati vengono rappresentati come contratti dati e contratti di messaggio; servizi di WCF e del flusso di lavoro utilizzano definizioni del contratto dati del contratto e il messaggio nell'ambito delle descrizioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="b6a00-104">The data is represented as data contracts and message contracts; both WCF and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="b6a00-105">Il servizio stesso espone metadati (nel formato WSDL) per descrivere le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="b6a00-105">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="b6a00-106">In WCF i contratti di servizio e i contratti di operazione definiscono il servizio e le operazioni supportate.</span><span class="sxs-lookup"><span data-stu-id="b6a00-106">In WCF, service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="b6a00-107">Tuttavia, in un servizio flusso di lavoro, questi contratti costituiscono parte del processo aziendale stesso e vengono esposti nei metadati da un processo denominato inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="b6a00-107">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="b6a00-108">Inferenza del contratto</span><span class="sxs-lookup"><span data-stu-id="b6a00-108">Contract Inference</span></span>  
 <span data-ttu-id="b6a00-109">Se un servizio flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene esaminata la definizione del flusso di lavoro e viene generato un contratto in base al set delle attività di messaggistica rilevato nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b6a00-109">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="b6a00-110">In particolare vengono utilizzate le attività e le proprietà indicate di seguito per generare il contratto:</span><span class="sxs-lookup"><span data-stu-id="b6a00-110">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="b6a00-111">Attività <xref:System.ServiceModel.Activities.Receive></span><span class="sxs-lookup"><span data-stu-id="b6a00-111"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <span data-ttu-id="b6a00-112">Attività <xref:System.ServiceModel.Activities.SendReply></span><span class="sxs-lookup"><span data-stu-id="b6a00-112"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <span data-ttu-id="b6a00-113">Attività <xref:System.ServiceModel.Activities.TransactedReceiveScope></span><span class="sxs-lookup"><span data-stu-id="b6a00-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="b6a00-114">Il risultato finale di inferenza del contratto rappresenta una descrizione del servizio utilizzando le stesse strutture dei dati del servizio WCF e dei contratti dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b6a00-114">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="b6a00-115">Queste informazioni vengono quindi usate per esporre WSDL per il servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b6a00-115">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a00-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a00-116">See also</span></span>

- [<span data-ttu-id="b6a00-117">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6a00-117">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="b6a00-118">Attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="b6a00-118">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
- [<span data-ttu-id="b6a00-119">Procedura: Creare un servizio del flusso di lavoro con attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="b6a00-119">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [<span data-ttu-id="b6a00-120">Procedura: Creare un servizio del flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="b6a00-120">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
