---
title: 'Procedura: creare un contratto Windows Communication Foundation con una classe'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e1a66dd00592e24fd505cb1956b04d2856bf96a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="8fced-102">Procedura: creare un contratto Windows Communication Foundation con una classe</span><span class="sxs-lookup"><span data-stu-id="8fced-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="8fced-103">La modalità preferita per creare un contratto [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è tramite un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8fced-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="8fced-104">Per altre informazioni, vedere [procedura: definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8fced-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="8fced-105">Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.</span><span class="sxs-lookup"><span data-stu-id="8fced-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8fced-106">`[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="8fced-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="8fced-107">La stessa situazione è valida per `[OperationContract]` e `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="8fced-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="8fced-108">In ogni caso il primo è l'abbreviazione del secondo.</span><span class="sxs-lookup"><span data-stu-id="8fced-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8fced-109"> i contratti di servizio, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8fced-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="8fced-110">Creazione di un contratto Windows Communication Foundation con una classe</span><span class="sxs-lookup"><span data-stu-id="8fced-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="8fced-111">Creare una nuova classe utilizzando Visual Basic, c# o qualsiasi altro linguaggio common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8fced-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="8fced-112">Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="8fced-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="8fced-113">Creare metodi nella classe.</span><span class="sxs-lookup"><span data-stu-id="8fced-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="8fced-114">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni metodo che deve essere esposto come parte del contratto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pubblico.</span><span class="sxs-lookup"><span data-stu-id="8fced-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fced-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fced-115">Example</span></span>  
 <span data-ttu-id="8fced-116">Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8fced-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="8fced-117">I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> utilizzano per impostazione predefinita un modello di messaggio request/reply.</span><span class="sxs-lookup"><span data-stu-id="8fced-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8fced-118"> Questo modello, vedere [procedura: creare un contratto Request/Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8fced-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="8fced-119">È anche possibile creare e usare altri modelli di messaggio impostando proprietà dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="8fced-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="8fced-120">Per ulteriori esempi, vedere [procedura: creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [procedura: creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8fced-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fced-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fced-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
