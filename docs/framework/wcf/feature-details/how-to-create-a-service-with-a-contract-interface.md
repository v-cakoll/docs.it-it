---
title: "Procedura: Creare un servizio con un'interfaccia di contratto"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 0aa5429d771aeda0b392b89ec4cc1a07de30973f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298539"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="8155d-102">Procedura: Creare un servizio con un'interfaccia di contratto</span><span class="sxs-lookup"><span data-stu-id="8155d-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="8155d-103">Il modo migliore per creare un contratto Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8155d-103">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="8155d-104">Questo contratto specifica la raccolta e la struttura dei messaggi necessari per accedere alle operazioni offerte dal servizio.</span><span class="sxs-lookup"><span data-stu-id="8155d-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="8155d-105">Questa interfaccia definisce i tipi di input e output applicando la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia e la classe <xref:System.ServiceModel.OperationContractAttribute> ai metodi che si desidera esporre.</span><span class="sxs-lookup"><span data-stu-id="8155d-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="8155d-106">Per altre informazioni sui contratti di servizio, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8155d-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="8155d-107">Creazione di un contratto WCF con un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8155d-107">Creating a WCF contract with an interface</span></span>  
  
1. <span data-ttu-id="8155d-108">Creare una nuova interfaccia utilizzando Visual Basic, C#, o qualsiasi altro linguaggio common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8155d-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="8155d-109">Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8155d-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3. <span data-ttu-id="8155d-110">Definire i metodi nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8155d-110">Define the methods in the interface.</span></span>  
  
4. <span data-ttu-id="8155d-111">Applicare il <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto pubblico di WCF.</span><span class="sxs-lookup"><span data-stu-id="8155d-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8155d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8155d-112">Example</span></span>  
 <span data-ttu-id="8155d-113">Nell'esempio di codice seguente viene illustrata un'interfaccia che definisce un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8155d-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="8155d-114">I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply.</span><span class="sxs-lookup"><span data-stu-id="8155d-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="8155d-115">Per altre informazioni su questo modello di messaggio, vedere [come: Creare un contratto Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8155d-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="8155d-116">È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="8155d-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="8155d-117">Per altri esempi, vedere [Procedura: Creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [come: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8155d-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8155d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8155d-118">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
