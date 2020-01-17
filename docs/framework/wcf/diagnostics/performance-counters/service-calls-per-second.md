---
title: 'Servizio: chiamate al secondo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: be5d77169a71d6f44205a1150da5239eceff7d9c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163904"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="999ce-102">Servizio: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="999ce-102">Service: Calls Per Second</span></span>
<span data-ttu-id="999ce-103">Nome contatore: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="999ce-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="999ce-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="999ce-104">Description</span></span>  
 <span data-ttu-id="999ce-105">Numero di chiamate al servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="999ce-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="999ce-106">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="999ce-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="999ce-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) dove il numeratore (N) rappresenta il numero di operazioni eseguite durante l'ultimo intervallo di campionamento, il denominatore (D) rappresenta il numero di tick trascorsi durante l'ultimo intervallo di campionamento e F è la frequenza dei tick.</span><span class="sxs-lookup"><span data-stu-id="999ce-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
