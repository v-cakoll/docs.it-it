---
title: 'Servizio: Chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167492"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="717ae-102">Servizio: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="717ae-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="717ae-103">Nome contatore: Chiamate non riuscite al secondo.</span><span class="sxs-lookup"><span data-stu-id="717ae-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="717ae-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="717ae-104">Description</span></span>  
 <span data-ttu-id="717ae-105">Numero di chiamate al secondo ricevute dal servizio aventi eccezioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="717ae-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="717ae-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="717ae-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="717ae-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="717ae-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="717ae-108">Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="717ae-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="717ae-109">Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="717ae-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="717ae-110">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questo servizio.</span><span class="sxs-lookup"><span data-stu-id="717ae-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717ae-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="717ae-111">See also</span></span>

- [<span data-ttu-id="717ae-112">Specifica e gestione di errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="717ae-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
