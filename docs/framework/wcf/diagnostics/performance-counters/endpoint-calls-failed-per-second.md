---
title: 'Endpoint: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: fa4fc1d8a875557f1da9e54e7a05eb012e7c221c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856348"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="abfde-102">Endpoint: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="abfde-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="abfde-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="abfde-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="abfde-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abfde-104">Description</span></span>  
 <span data-ttu-id="abfde-105">Numero di chiamate al secondo con eccezioni non gestite ricevute dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="abfde-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="abfde-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="abfde-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="abfde-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="abfde-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="abfde-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="abfde-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfde-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abfde-109">See Also</span></span>  
 [<span data-ttu-id="abfde-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="abfde-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
