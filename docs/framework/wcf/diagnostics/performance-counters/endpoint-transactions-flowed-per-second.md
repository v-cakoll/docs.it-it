---
title: 'Endpoint: transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 39458dcb6ac033fd5084b5f2e760e0e26c345da7
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163553"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="13024-102">Endpoint: transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="13024-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="13024-103">Nome contatore: transazioni propagate al secondo.</span><span class="sxs-lookup"><span data-stu-id="13024-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="13024-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13024-104">Description</span></span>  
 <span data-ttu-id="13024-105">Numero di transazioni propagate alle operazioni per l'endpoint al secondo.</span><span class="sxs-lookup"><span data-stu-id="13024-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="13024-106">Questo contatore viene incrementato ogni volta che è presente un ID di transazione nel messaggio inviato all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="13024-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="13024-107">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="13024-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="13024-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="13024-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
