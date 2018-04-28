---
title: Implementazione dei contratti di servizio
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a9c34f67de6f4f8b4a8d22dac7e8bf1c9555498
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="f9ad6-102">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="f9ad6-102">Implementing Service Contracts</span></span>
<span data-ttu-id="f9ad6-103">Un servizio è una classe che espone le funzionalità disponibili per i client a uno o più endpoint.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="f9ad6-104">Per creare un servizio, scrivere una classe che implementi un contratto [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ad6-104">To create a service, write a class that implements a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] contract.</span></span> <span data-ttu-id="f9ad6-105">Questa operazione può essere eseguita in due modi.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-105">You can do this in one of two ways.</span></span> <span data-ttu-id="f9ad6-106">È possibile definire il contratto separatamente come un'interfaccia e quindi creare una classe che implementi tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="f9ad6-107">In alternativa, è possibile creare direttamente la classe e il contratto posizionando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> sulla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> sui metodi disponibili per i client del servizio.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="f9ad6-108">Creazione di una classe di servizio</span><span class="sxs-lookup"><span data-stu-id="f9ad6-108">Creating a service class</span></span>  
 <span data-ttu-id="f9ad6-109">Nell'esempio seguente viene illustrato un servizio che implementa un contratto `IMath` definito separatamente.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="f9ad6-110">In alternativa, un servizio può esporre direttamente un contratto.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="f9ad6-111">Nell'esempio seguente viene illustrata una classe di servizio che definisce e implementa un contratto `MathService`.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="f9ad6-112">Si noti che i servizi precedenti espongono contratti diversi perché i nomi di contratto sono diversi.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="f9ad6-113">Nel primo caso, il contratto esposto è denominato "`IMath`" mentre nel secondo caso il contratto è denominato "`MathService`".</span><span class="sxs-lookup"><span data-stu-id="f9ad6-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="f9ad6-114">È possibile impostare alcuni aspetti a livello del servizio e dell'implementazione dell'operazione, ad esempio la concorrenza e la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="f9ad6-115">Per altre informazioni, vedere [progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad6-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="f9ad6-116">Dopo avere implementato un contratto di servizio, è necessario creare uno o più endpoint per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="f9ad6-117">Per altre informazioni, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad6-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f9ad6-118"> come eseguire un servizio, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad6-118"> how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ad6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9ad6-119">See Also</span></span>  
 [<span data-ttu-id="f9ad6-120">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="f9ad6-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="f9ad6-121">Procedura: Creare un servizio con una classe di contratto</span><span class="sxs-lookup"><span data-stu-id="f9ad6-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)  
 [<span data-ttu-id="f9ad6-122">Procedura: Creare un servizio con un'interfaccia di contratto</span><span class="sxs-lookup"><span data-stu-id="f9ad6-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)  
 [<span data-ttu-id="f9ad6-123">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="f9ad6-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
