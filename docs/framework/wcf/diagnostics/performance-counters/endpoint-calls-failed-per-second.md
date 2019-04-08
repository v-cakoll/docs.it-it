---
title: 'Endpoint: Chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100026"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="ec6be-102">Endpoint: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="ec6be-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="ec6be-103">Nome contatore: Chiamate non riuscite al secondo.</span><span class="sxs-lookup"><span data-stu-id="ec6be-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec6be-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec6be-104">Description</span></span>  
 <span data-ttu-id="ec6be-105">Numero di chiamate al secondo con eccezioni non gestite ricevute dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ec6be-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ec6be-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="ec6be-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ec6be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ec6be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ec6be-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ec6be-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6be-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec6be-109">See also</span></span>

- [<span data-ttu-id="ec6be-110">Specifica e gestione di errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="ec6be-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
