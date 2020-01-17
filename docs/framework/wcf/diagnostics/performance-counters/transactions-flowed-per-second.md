---
title: Transazioni propagate al secondo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: 8b6077af3f98f7a205772b4883dc122374083e00
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163826"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="2a23b-102">Transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="2a23b-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="2a23b-103">Nome contatore: transazioni propagate al secondo.</span><span class="sxs-lookup"><span data-stu-id="2a23b-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="2a23b-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a23b-104">Description</span></span>  
 <span data-ttu-id="2a23b-105">Numero di transazioni propagate a questa operazione in un secondo.</span><span class="sxs-lookup"><span data-stu-id="2a23b-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="2a23b-106">Questo contatore viene incrementato ogni volta che è presente un ID di transazione in un messaggio inviato all'operazione.</span><span class="sxs-lookup"><span data-stu-id="2a23b-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="2a23b-107">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="2a23b-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2a23b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2a23b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
