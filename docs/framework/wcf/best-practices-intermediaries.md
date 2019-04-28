---
title: 'Procedure consigliate: Intermediari'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 0bd553486bfb89a0ec14c42a1bb7d2ed9c4c540d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608905"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="e38cc-102">Procedure consigliate: Intermediari</span><span class="sxs-lookup"><span data-stu-id="e38cc-102">Best Practices: Intermediaries</span></span>
<span data-ttu-id="e38cc-103">Assicurarsi di gestire gli errori correttamente nella chiamata agli intermediari verificando che i canali lato servizio degli intermediari vengano chiusi in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="e38cc-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="e38cc-104">Si consideri lo scenario seguente.</span><span class="sxs-lookup"><span data-stu-id="e38cc-104">Consider the following scenario.</span></span> <span data-ttu-id="e38cc-105">Un client esegue una chiamata a un intermediario che quindi chiama un servizio back-end.</span><span class="sxs-lookup"><span data-stu-id="e38cc-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="e38cc-106">Il servizio back-end non definisce contratti di errori, pertanto qualsiasi errore generato da questo servizio verrà considerato come errore non tipizzato.</span><span class="sxs-lookup"><span data-stu-id="e38cc-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="e38cc-107">Il servizio back-end genera un <xref:System.ApplicationException> e WCF viene correttamente interrotto il canale lato servizio.</span><span class="sxs-lookup"><span data-stu-id="e38cc-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="e38cc-108">L'oggetto <xref:System.ApplicationException> viene quindi rilevato come oggetto <xref:System.ServiceModel.FaultException> generato per l'intermediario.</span><span class="sxs-lookup"><span data-stu-id="e38cc-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="e38cc-109">L'intermediario genera nuovamente l'oggetto <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="e38cc-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="e38cc-110">In WCF l'eccezione viene interpretata come errore non tipizzato proveniente dall'intermediario e inoltrata al client.</span><span class="sxs-lookup"><span data-stu-id="e38cc-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="e38cc-111">Alla ricezione dell'errore, sia l'intermediario che il client lo imputano ai rispettivi canali lato client.</span><span class="sxs-lookup"><span data-stu-id="e38cc-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="e38cc-112">Il canale lato servizio dell'intermediario rimane tuttavia aperto perché non viene rilevato che l'errore è irreversibile.</span><span class="sxs-lookup"><span data-stu-id="e38cc-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="e38cc-113">La procedura consigliata in questo scenario è rilevare se l'errore proveniente dal servizio è irreversibile. In caso affermativo, l'intermediario dovrebbe bloccare il proprio canale lato servizio come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="e38cc-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e38cc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e38cc-114">See also</span></span>

- [<span data-ttu-id="e38cc-115">Gestione errori WCF</span><span class="sxs-lookup"><span data-stu-id="e38cc-115">WCF Error Handling</span></span>](../../../docs/framework/wcf/wcf-error-handling.md)
- [<span data-ttu-id="e38cc-116">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="e38cc-116">Specifying and Handling Faults in Contracts and Services</span></span>](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
