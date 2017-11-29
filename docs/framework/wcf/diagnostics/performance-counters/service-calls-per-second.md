---
title: 'Servizio: chiamate al secondo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 940249c4ec0317013efcb03aafc11d384ec0363f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-per-second"></a><span data-ttu-id="8ad4e-102">Servizio: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="8ad4e-102">Service: Calls Per Second</span></span>
<span data-ttu-id="8ad4e-103">Nome contatore: chiamate al secondo</span><span class="sxs-lookup"><span data-stu-id="8ad4e-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ad4e-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ad4e-104">Description</span></span>  
 <span data-ttu-id="8ad4e-105">Numero di chiamate al servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="8ad4e-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="8ad4e-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="8ad4e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8ad4e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) dove il numeratore (N) rappresenta il numero di operazioni eseguite durante l'ultimo intervallo di campionamento, il denominatore (D) rappresenta il numero di tick trascorsi durante l'ultimo intervallo di campionamento e F è la frequenza dei tick.</span><span class="sxs-lookup"><span data-stu-id="8ad4e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
