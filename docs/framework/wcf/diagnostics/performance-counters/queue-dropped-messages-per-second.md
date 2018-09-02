---
title: Messaggi in coda eliminati al secondo
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418248"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="85335-102">Messaggi in coda eliminati al secondo</span><span class="sxs-lookup"><span data-stu-id="85335-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="85335-103">Nome contatore: messaggi in coda eliminati al secondo</span><span class="sxs-lookup"><span data-stu-id="85335-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="85335-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85335-104">Description</span></span>  
 <span data-ttu-id="85335-105">Numero di messaggi eliminati dal trasporto in coda di questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="85335-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="85335-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="85335-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="85335-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="85335-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
