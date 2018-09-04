---
title: Operazioni transazionali con commit eseguito al secondo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564011"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="a17c3-102">Operazioni transazionali con commit eseguito al secondo</span><span class="sxs-lookup"><span data-stu-id="a17c3-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="a17c3-103">Nome contatore: operazioni transazionali con commit eseguito al secondo.</span><span class="sxs-lookup"><span data-stu-id="a17c3-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a17c3-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a17c3-104">Description</span></span>  
 <span data-ttu-id="a17c3-105">Numero di operazioni transazionali di cui è stato eseguito il commit in questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="a17c3-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="a17c3-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="a17c3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a17c3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a17c3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
