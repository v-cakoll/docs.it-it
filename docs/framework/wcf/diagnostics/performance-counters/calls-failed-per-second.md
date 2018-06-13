---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 19f09b2a2132cab56da5dec49bdc8d5f5e4c8b8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474454"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="56883-102">Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="56883-102">Calls Failed Per Second</span></span>
<span data-ttu-id="56883-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="56883-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="56883-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56883-104">Description</span></span>  
 <span data-ttu-id="56883-105">Numero di chiamate al secondo con eccezioni non gestite presenti in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="56883-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="56883-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="56883-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="56883-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="56883-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="56883-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="56883-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56883-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56883-109">See Also</span></span>  
 [<span data-ttu-id="56883-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="56883-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
