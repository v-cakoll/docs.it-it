---
title: 'Servizio: chiamate al secondo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: c23456f49eb867d5b6f66b4386a83615d95e07da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473928"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="4b45a-102">Servizio: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="4b45a-102">Service: Calls Per Second</span></span>
<span data-ttu-id="4b45a-103">Nome contatore: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="4b45a-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b45a-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b45a-104">Description</span></span>  
 <span data-ttu-id="4b45a-105">Numero di chiamate al servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="4b45a-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="4b45a-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="4b45a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4b45a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) dove il numeratore (N) rappresenta il numero di operazioni eseguite durante l'ultimo intervallo di campionamento, il denominatore (D) rappresenta il numero di tick trascorsi durante l'ultimo intervallo di campionamento e F è la frequenza dei tick.</span><span class="sxs-lookup"><span data-stu-id="4b45a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
