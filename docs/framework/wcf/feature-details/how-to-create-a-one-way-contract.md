---
title: 'Procedura: creare un contratto unidirezionale'
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
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d08fcb955c972ffbd7ef0a48625f1005ab366dd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-one-way-contract"></a><span data-ttu-id="3ca31-102">Procedura: creare un contratto unidirezionale</span><span class="sxs-lookup"><span data-stu-id="3ca31-102">How to: Create a One-Way Contract</span></span>
<span data-ttu-id="3ca31-103">In questo argomento vengono illustrati i passaggi di base per creare metodi che utilizzano un contratto unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="3ca31-103">This topic shows the basic steps to create methods that use a one-way contract.</span></span> <span data-ttu-id="3ca31-104">Tali metodi richiamano operazioni in un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] da un client senza però aspettarsi una risposta.</span><span class="sxs-lookup"><span data-stu-id="3ca31-104">Such methods invoke operations on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service from a client but do not expect a reply.</span></span> <span data-ttu-id="3ca31-105">Questo tipo di contratto può essere utilizzato, ad esempio, per pubblicare notifiche a numerosi sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="3ca31-105">This type of contract can be used, for example, to publish notifications to many subscribers.</span></span> <span data-ttu-id="3ca31-106">È anche possibile utilizzare contratti unidirezionali durante la creazione di un contratto duplex (bidirezionale) che consente ai client e ai server di comunicare fra loro indipendentemente in modo che uno sia in grado di avviare chiamate all'altro.</span><span class="sxs-lookup"><span data-stu-id="3ca31-106">You can also use one-way contracts when creating a duplex (two-way) contract, which allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="3ca31-107">In particolare, questo può consentire al server di eseguire chiamate unidirezionali al client che vengono trattate da quest'ultimo come eventi.</span><span class="sxs-lookup"><span data-stu-id="3ca31-107">This can allow, in particular, the server to make one-way calls to the client that the client can treat as events.</span></span> <span data-ttu-id="3ca31-108">Per informazioni dettagliate sulla specifica di metodi bidirezionali, vedere la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> e la classe <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3ca31-108">For detailed information about specifying one-way methods, see the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property and the <xref:System.ServiceModel.OperationContractAttribute> class.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="3ca31-109">creazione di un'applicazione client per un contratto duplex, vedere [come: Access Services con unidirezionale e contratti Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="3ca31-109"> creating a client application for a duplex contract, see [How to: Access Services with One-Way and Request-Reply Contracts](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span></span> <span data-ttu-id="3ca31-110">Per un esempio funzionante, vedere il [unidirezionale](../../../../docs/framework/wcf/samples/one-way.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="3ca31-110">For a working sample, see the [One-Way](../../../../docs/framework/wcf/samples/one-way.md) sample.</span></span>  
  
### <a name="to-create-a-one-way-contract"></a><span data-ttu-id="3ca31-111">Per creare un contratto unidirezionale</span><span class="sxs-lookup"><span data-stu-id="3ca31-111">To create a one-way contract</span></span>  
  
1.  <span data-ttu-id="3ca31-112">Creare il contratto di servizio applicando la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia e che definisce i metodi del servizio da implementare.</span><span class="sxs-lookup"><span data-stu-id="3ca31-112">Create the service contract by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface that defines the methods the service is to implement.</span></span>  
  
2.  <span data-ttu-id="3ca31-113">Indicare quali metodi nell'interfaccia possono essere chiamati da un client applicando loro la classe <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3ca31-113">Indicate which methods in the interface a client can invoked by applying the <xref:System.ServiceModel.OperationContractAttribute> class to them.</span></span>  
  
3.  <span data-ttu-id="3ca31-114">Designare operazioni che non devono avere output (nessun valore restituito e nessun parametro out o ref) di tipo unidirezionale impostando la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="3ca31-114">Designate operations that must have no output (no return value and no out or ref parameters) as one-way by setting the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true`.</span></span> <span data-ttu-id="3ca31-115">Notare che le operazioni che contengono la classe <xref:System.ServiceModel.OperationContractAttribute> soddisfano per impostazione predefinita un contratto request/reply perché la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> è `false` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ca31-115">Note that the operations that carry the <xref:System.ServiceModel.OperationContractAttribute> class satisfy a request-reply contract by default because the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property is `false` by default.</span></span> <span data-ttu-id="3ca31-116">Pertanto, se si desidera un contratto unidirezionale per il metodo, è necessario specificare in modo esplicito il valore della proprietà dell'attributo in modo che sia `true`.</span><span class="sxs-lookup"><span data-stu-id="3ca31-116">So you must explicitly specify the value of the attribute property to be `true` if you want a one-way contract for the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ca31-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ca31-117">Example</span></span>  
 <span data-ttu-id="3ca31-118">Nell'esempio di codice seguente viene definito un contratto per un servizio che include alcuni metodi unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="3ca31-118">The following code example defines a contract for a service that includes several one-way methods.</span></span> <span data-ttu-id="3ca31-119">Tutti i metodi contengono contratti unidirezionali eccetto `Equals` la cui impostazione predefinita è request/reply e restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="3ca31-119">All of the methods have one-way contracts except `Equals`, which defaults to request-reply and returns a result.</span></span>  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3ca31-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca31-120">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="3ca31-121">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="3ca31-121">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="3ca31-122">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="3ca31-122">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="3ca31-123">Sessione</span><span class="sxs-lookup"><span data-stu-id="3ca31-123">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)  
 [<span data-ttu-id="3ca31-124">Procedura: Creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="3ca31-124">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
