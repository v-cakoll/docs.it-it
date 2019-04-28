---
title: Messaggi in coda eliminati al secondo
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916162"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="c27cb-102">Messaggi in coda eliminati al secondo</span><span class="sxs-lookup"><span data-stu-id="c27cb-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="c27cb-103">Nome contatore: I messaggi in coda eliminati al secondo.</span><span class="sxs-lookup"><span data-stu-id="c27cb-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c27cb-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c27cb-104">Description</span></span>  
 <span data-ttu-id="c27cb-105">Numero di messaggi eliminati dal trasporto in coda di questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="c27cb-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="c27cb-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="c27cb-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c27cb-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c27cb-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
