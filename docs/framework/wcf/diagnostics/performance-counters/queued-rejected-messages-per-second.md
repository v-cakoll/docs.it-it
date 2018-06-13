---
title: Messaggi in coda rifiutati al secondo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 31091c6c9dd04ecd7294f69f9611f25e401df724
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473445"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="15e2e-102">Messaggi in coda rifiutati al secondo</span><span class="sxs-lookup"><span data-stu-id="15e2e-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="15e2e-103">Nome contatore: messaggi in coda rifiutati al secondo</span><span class="sxs-lookup"><span data-stu-id="15e2e-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="15e2e-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15e2e-104">Description</span></span>  
 <span data-ttu-id="15e2e-105">Numero di messaggi rifiutati dal trasporto in coda di questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="15e2e-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="15e2e-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="15e2e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="15e2e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="15e2e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
