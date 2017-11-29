---
title: 'Procedura: creare un contratto Windows Communication Foundation con una classe'
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
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bf32559f9b5a1040390562cc8492646288494638
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="728b5-102">Procedura: creare un contratto Windows Communication Foundation con una classe</span><span class="sxs-lookup"><span data-stu-id="728b5-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="728b5-103">La modalità preferita per creare un contratto [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è tramite un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="728b5-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="728b5-104">[Procedura: definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="728b5-104"> [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="728b5-105">Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.</span><span class="sxs-lookup"><span data-stu-id="728b5-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="728b5-106">`[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="728b5-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="728b5-107">La stessa situazione è valida per `[OperationContract]` e `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="728b5-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="728b5-108">In ogni caso il primo è l'abbreviazione del secondo.</span><span class="sxs-lookup"><span data-stu-id="728b5-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="728b5-109">contratti di servizio, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="728b5-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="728b5-110">Creazione di un contratto Windows Communication Foundation con una classe</span><span class="sxs-lookup"><span data-stu-id="728b5-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="728b5-111">Creare una nuova classe utilizzando [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# o qualsiasi altro linguaggio Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="728b5-111">Create a new class using [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="728b5-112">Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="728b5-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="728b5-113">Creare metodi nella classe.</span><span class="sxs-lookup"><span data-stu-id="728b5-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="728b5-114">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni metodo che deve essere esposto come parte del contratto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pubblico.</span><span class="sxs-lookup"><span data-stu-id="728b5-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="728b5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="728b5-115">Example</span></span>  
 <span data-ttu-id="728b5-116">Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="728b5-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="728b5-117">I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> utilizzano per impostazione predefinita un modello di messaggio request/reply.</span><span class="sxs-lookup"><span data-stu-id="728b5-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="728b5-118">Questo modello di messaggio, vedere [procedura: creare un contratto Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="728b5-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="728b5-119">È anche possibile creare e usare altri modelli di messaggio impostando proprietà dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="728b5-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="728b5-120">Per ulteriori esempi, vedere [procedura: creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [procedura: creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="728b5-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="728b5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="728b5-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
