---
title: 'Endpoint: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 25e504221097505e622a3ba60f0c7e85ec455f36
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163618"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="18b40-102">Endpoint: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="18b40-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="18b40-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="18b40-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="18b40-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18b40-104">Description</span></span>  
 <span data-ttu-id="18b40-105">Numero di chiamate al secondo con eccezioni non gestite ricevute dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="18b40-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="18b40-106">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="18b40-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="18b40-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="18b40-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="18b40-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="18b40-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b40-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18b40-109">See also</span></span>

- [<span data-ttu-id="18b40-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="18b40-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
