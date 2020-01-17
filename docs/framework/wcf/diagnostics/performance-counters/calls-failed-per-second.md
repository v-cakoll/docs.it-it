---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 110ee5c264094f80d5c7c6542c3e388e758e1665
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163163"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="58801-102">Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="58801-102">Calls Failed Per Second</span></span>
<span data-ttu-id="58801-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="58801-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="58801-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58801-104">Description</span></span>  
 <span data-ttu-id="58801-105">Numero di chiamate al secondo con eccezioni non gestite presenti in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="58801-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="58801-106">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="58801-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="58801-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="58801-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="58801-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="58801-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58801-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58801-109">See also</span></span>

- [<span data-ttu-id="58801-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="58801-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
