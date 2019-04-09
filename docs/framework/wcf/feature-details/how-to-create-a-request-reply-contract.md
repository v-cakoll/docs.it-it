---
title: 'Procedura: Creare un contratto Request/Reply'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 9954be556df13193c290a55616ad83ef07e0af7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141076"
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="840fb-102">Procedura: Creare un contratto Request/Reply</span><span class="sxs-lookup"><span data-stu-id="840fb-102">How to: Create a Request-Reply Contract</span></span>
<span data-ttu-id="840fb-103">Un contratto di tipo request/reply specifica un metodo che restituisce una risposta</span><span class="sxs-lookup"><span data-stu-id="840fb-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="840fb-104">La replica deve essere inviata e correlata alla richiesta in base ai termini di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="840fb-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="840fb-105">Anche se il metodo non restituisce alcuna risposta (`void` in C# o `Sub` in Visual Basic), nell'infrastruttura viene creato e inviato un messaggio vuoto al chiamante.</span><span class="sxs-lookup"><span data-stu-id="840fb-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="840fb-106">Per impedire l'invio di un messaggio di risposta vuoto, utilizzare un contratto unidirezionale per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="840fb-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="840fb-107">Per creare un contratto request/reply</span><span class="sxs-lookup"><span data-stu-id="840fb-107">To create a request-reply contract</span></span>  
  
1.  <span data-ttu-id="840fb-108">Creare un'interfaccia nel linguaggio di programmazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="840fb-108">Create an interface in the programming language of your choice.</span></span>  
  
2.  <span data-ttu-id="840fb-109">Applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="840fb-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3.  <span data-ttu-id="840fb-110">Applicare l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ciascun metodo che i client possono richiamare.</span><span class="sxs-lookup"><span data-stu-id="840fb-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4.  <span data-ttu-id="840fb-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="840fb-111">Optional.</span></span> <span data-ttu-id="840fb-112">Impostare il valore della proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true` per impedire l'invio di un messaggio di risposta vuoto.</span><span class="sxs-lookup"><span data-stu-id="840fb-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="840fb-113">Per impostazione predefinita, tutte le operazioni sono contratti di tipo request/reply.</span><span class="sxs-lookup"><span data-stu-id="840fb-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="840fb-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="840fb-114">Example</span></span>  
 <span data-ttu-id="840fb-115">Nell'esempio seguente è definito un contratto per un servizio calcolatrice che fornisce metodi `Add` e `Subtract`.</span><span class="sxs-lookup"><span data-stu-id="840fb-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="840fb-116">Il metodo `Multiply` privato non fa parte del contratto perché non è contrassegnato dalla classe <xref:System.ServiceModel.OperationContractAttribute> e quindi non è accessibile ai client.</span><span class="sxs-lookup"><span data-stu-id="840fb-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
-   <span data-ttu-id="840fb-117">Per altre informazioni su come specificare contratti di operazione, vedere la <xref:System.ServiceModel.OperationContractAttribute> classi e <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="840fb-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
-   <span data-ttu-id="840fb-118">L'applicazione degli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> determina la generazione automatica delle definizioni del contratto di servizio in un documento del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) dopo la distribuzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="840fb-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="840fb-119">Il documento viene scaricato aggiungendo l'elemento `?wsdl` all'indirizzo di base HTTP per il servizio,</span><span class="sxs-lookup"><span data-stu-id="840fb-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="840fb-120">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="840fb-120">For example,</span></span> `http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a><span data-ttu-id="840fb-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="840fb-121">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="840fb-122">Progettazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="840fb-122">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)
- [<span data-ttu-id="840fb-123">Procedura: Creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="840fb-123">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
