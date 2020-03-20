---
title: Implementazione dei contratti di servizio
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: aefe146a8941d98d7d9138e4ece83c330c967034
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183997"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="1946e-102">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="1946e-102">Implementing Service Contracts</span></span>
<span data-ttu-id="1946e-103">Un servizio è una classe che espone le funzionalità disponibili per i client a uno o più endpoint.</span><span class="sxs-lookup"><span data-stu-id="1946e-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="1946e-104">Per creare un servizio, scrivere una classe che implementa un contratto Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1946e-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="1946e-105">Questa operazione può essere eseguita in due modi.</span><span class="sxs-lookup"><span data-stu-id="1946e-105">You can do this in one of two ways.</span></span> <span data-ttu-id="1946e-106">È possibile definire il contratto separatamente come un'interfaccia e quindi creare una classe che implementi tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1946e-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="1946e-107">In alternativa, è possibile creare direttamente la classe e il contratto posizionando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> sulla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> sui metodi disponibili per i client del servizio.</span><span class="sxs-lookup"><span data-stu-id="1946e-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="1946e-108">Creazione di una classe di servizio</span><span class="sxs-lookup"><span data-stu-id="1946e-108">Creating a service class</span></span>  
 <span data-ttu-id="1946e-109">Nell'esempio seguente viene illustrato un servizio che implementa un contratto `IMath` definito separatamente.</span><span class="sxs-lookup"><span data-stu-id="1946e-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
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
  
 <span data-ttu-id="1946e-110">In alternativa, un servizio può esporre direttamente un contratto.</span><span class="sxs-lookup"><span data-stu-id="1946e-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="1946e-111">Nell'esempio seguente viene illustrata una classe di servizio che definisce e implementa un contratto `MathService`.</span><span class="sxs-lookup"><span data-stu-id="1946e-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
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
  
 <span data-ttu-id="1946e-112">Si noti che i servizi precedenti espongono contratti diversi perché i nomi di contratto sono diversi.</span><span class="sxs-lookup"><span data-stu-id="1946e-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="1946e-113">Nel primo caso, il contratto esposto è denominato "`IMath`" mentre nel secondo caso il contratto è denominato "`MathService`".</span><span class="sxs-lookup"><span data-stu-id="1946e-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="1946e-114">È possibile impostare alcuni aspetti a livello del servizio e dell'implementazione dell'operazione, ad esempio la concorrenza e la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="1946e-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="1946e-115">Per ulteriori informazioni, vedere [Progettazione e implementazione di servizi](designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="1946e-115">For more information, see [Designing and Implementing Services](designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="1946e-116">Dopo avere implementato un contratto di servizio, è necessario creare uno o più endpoint per il servizio.</span><span class="sxs-lookup"><span data-stu-id="1946e-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="1946e-117">Per ulteriori informazioni, vedere [Cenni preliminari sulla creazione di endpoint.](endpoint-creation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1946e-117">For more information, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="1946e-118">Per ulteriori informazioni su come eseguire un servizio, vedere [Servizi di hosting](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="1946e-118">For more information about how to run a service, see [Hosting Services](hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1946e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1946e-119">See also</span></span>

- [<span data-ttu-id="1946e-120">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="1946e-120">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)
- [<span data-ttu-id="1946e-121">Procedura: creare un servizio con una classe Contract</span><span class="sxs-lookup"><span data-stu-id="1946e-121">How to: Create a Service with a Contract Class</span></span>](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [<span data-ttu-id="1946e-122">Procedura: creare un servizio con un'interfaccia di contratto</span><span class="sxs-lookup"><span data-stu-id="1946e-122">How to: Create a Service with a Contract Interface</span></span>](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [<span data-ttu-id="1946e-123">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="1946e-123">Specifying Service Run-Time Behavior</span></span>](specifying-service-run-time-behavior.md)
