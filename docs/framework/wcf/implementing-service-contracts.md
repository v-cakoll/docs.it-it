---
title: Implementazione dei contratti di servizio
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: d22d0ada44ca4374da0b8feccf0a37ff1016dc80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576499"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="c974c-102">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="c974c-102">Implementing Service Contracts</span></span>
<span data-ttu-id="c974c-103">Un servizio è una classe che espone le funzionalità disponibili per i client a uno o più endpoint.</span><span class="sxs-lookup"><span data-stu-id="c974c-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="c974c-104">Per creare un servizio, scrivere una classe che implementa un contratto Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c974c-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="c974c-105">Questa operazione può essere eseguita in due modi.</span><span class="sxs-lookup"><span data-stu-id="c974c-105">You can do this in one of two ways.</span></span> <span data-ttu-id="c974c-106">È possibile definire il contratto separatamente come un'interfaccia e quindi creare una classe che implementi tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c974c-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="c974c-107">In alternativa, è possibile creare direttamente la classe e il contratto posizionando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> sulla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> sui metodi disponibili per i client del servizio.</span><span class="sxs-lookup"><span data-stu-id="c974c-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="c974c-108">Creazione di una classe di servizio</span><span class="sxs-lookup"><span data-stu-id="c974c-108">Creating a service class</span></span>  
 <span data-ttu-id="c974c-109">Nell'esempio seguente viene illustrato un servizio che implementa un contratto `IMath` definito separatamente.</span><span class="sxs-lookup"><span data-stu-id="c974c-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
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
  
 <span data-ttu-id="c974c-110">In alternativa, un servizio può esporre direttamente un contratto.</span><span class="sxs-lookup"><span data-stu-id="c974c-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="c974c-111">Nell'esempio seguente viene illustrata una classe di servizio che definisce e implementa un contratto `MathService`.</span><span class="sxs-lookup"><span data-stu-id="c974c-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
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
  
 <span data-ttu-id="c974c-112">Si noti che i servizi precedenti espongono contratti diversi perché i nomi di contratto sono diversi.</span><span class="sxs-lookup"><span data-stu-id="c974c-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="c974c-113">Nel primo caso, il contratto esposto è denominato "`IMath`" mentre nel secondo caso il contratto è denominato "`MathService`".</span><span class="sxs-lookup"><span data-stu-id="c974c-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="c974c-114">È possibile impostare alcuni aspetti a livello del servizio e dell'implementazione dell'operazione, ad esempio la concorrenza e la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="c974c-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="c974c-115">Per altre informazioni, vedere [progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="c974c-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="c974c-116">Dopo avere implementato un contratto di servizio, è necessario creare uno o più endpoint per il servizio.</span><span class="sxs-lookup"><span data-stu-id="c974c-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="c974c-117">Per altre informazioni, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c974c-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="c974c-118">Per altre informazioni su come eseguire un servizio, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c974c-118">For more information about how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c974c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c974c-119">See also</span></span>
- [<span data-ttu-id="c974c-120">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="c974c-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="c974c-121">Procedura: Creare un servizio con una classe del contratto</span><span class="sxs-lookup"><span data-stu-id="c974c-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [<span data-ttu-id="c974c-122">Procedura: Creare un servizio con un'interfaccia del contratto</span><span class="sxs-lookup"><span data-stu-id="c974c-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [<span data-ttu-id="c974c-123">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="c974c-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
