---
title: Messaggi in coda rifiutati al secondo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916188"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="8c63c-102">Messaggi in coda rifiutati al secondo</span><span class="sxs-lookup"><span data-stu-id="8c63c-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="8c63c-103">Nome contatore: Messaggi in coda rifiutati al secondo.</span><span class="sxs-lookup"><span data-stu-id="8c63c-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8c63c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c63c-104">Description</span></span>  
 <span data-ttu-id="8c63c-105">Numero di messaggi rifiutati dal trasporto in coda di questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="8c63c-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="8c63c-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="8c63c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8c63c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8c63c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
