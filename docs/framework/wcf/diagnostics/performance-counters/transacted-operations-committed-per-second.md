---
title: Operazioni transazionali con commit eseguito al secondo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 3bec51a7be63c54a240b85032ecac09b87173393
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474272"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="02359-102">Operazioni transazionali con commit eseguito al secondo</span><span class="sxs-lookup"><span data-stu-id="02359-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="02359-103">Nome contatore: operazioni transazionali con commit eseguito al secondo.</span><span class="sxs-lookup"><span data-stu-id="02359-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="02359-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02359-104">Description</span></span>  
 <span data-ttu-id="02359-105">Numero di operazioni transazionali di cui è stato eseguito il commit in questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="02359-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="02359-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="02359-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="02359-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="02359-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
