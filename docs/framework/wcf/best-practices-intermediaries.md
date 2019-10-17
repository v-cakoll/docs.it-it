---
title: 'Procedure consigliate: intermediari'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: a7c037b5942a404b1ff790638979a8e430394151
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320790"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="23f40-102">Procedure consigliate: intermediari</span><span class="sxs-lookup"><span data-stu-id="23f40-102">Best Practices: Intermediaries</span></span>
<span data-ttu-id="23f40-103">Assicurarsi di gestire gli errori correttamente nella chiamata agli intermediari verificando che i canali lato servizio degli intermediari vengano chiusi in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="23f40-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="23f40-104">Si consideri lo scenario seguente.</span><span class="sxs-lookup"><span data-stu-id="23f40-104">Consider the following scenario.</span></span> <span data-ttu-id="23f40-105">Un client esegue una chiamata a un intermediario che quindi chiama un servizio back-end.</span><span class="sxs-lookup"><span data-stu-id="23f40-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="23f40-106">Il servizio back-end non definisce contratti di errori, pertanto qualsiasi errore generato da questo servizio verrà considerato come errore non tipizzato.</span><span class="sxs-lookup"><span data-stu-id="23f40-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="23f40-107">Il servizio back-end genera un'<xref:System.ApplicationException> e WCF interrompe correttamente il canale sul lato servizio.</span><span class="sxs-lookup"><span data-stu-id="23f40-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="23f40-108">L'oggetto <xref:System.ApplicationException> viene quindi rilevato come oggetto <xref:System.ServiceModel.FaultException> generato per l'intermediario.</span><span class="sxs-lookup"><span data-stu-id="23f40-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="23f40-109">L'intermediario genera nuovamente l'oggetto <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="23f40-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="23f40-110">In WCF l'eccezione viene interpretata come errore non tipizzato proveniente dall'intermediario e inoltrata al client.</span><span class="sxs-lookup"><span data-stu-id="23f40-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="23f40-111">Alla ricezione dell'errore, sia l'intermediario che il client lo imputano ai rispettivi canali lato client.</span><span class="sxs-lookup"><span data-stu-id="23f40-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="23f40-112">Il canale lato servizio dell'intermediario rimane tuttavia aperto perché non viene rilevato che l'errore è irreversibile.</span><span class="sxs-lookup"><span data-stu-id="23f40-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="23f40-113">La procedura consigliata in questo scenario è rilevare se l'errore proveniente dal servizio è irreversibile. In caso affermativo, l'intermediario dovrebbe bloccare il proprio canale lato servizio come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="23f40-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23f40-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23f40-114">See also</span></span>

- [<span data-ttu-id="23f40-115">Gestione errori WCF</span><span class="sxs-lookup"><span data-stu-id="23f40-115">WCF Error Handling</span></span>](wcf-error-handling.md)
- [<span data-ttu-id="23f40-116">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="23f40-116">Specifying and Handling Faults in Contracts and Services</span></span>](specifying-and-handling-faults-in-contracts-and-services.md)
