---
title: Operazioni transazionali interrotte ogni secondo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: dacdf93f4610df9161134a41ece19fd2a18637c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474532"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="6d640-102">Operazioni transazionali interrotte ogni secondo</span><span class="sxs-lookup"><span data-stu-id="6d640-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="6d640-103">Nome contatorte: operazioni transazionali interrotte ogni secondo.</span><span class="sxs-lookup"><span data-stu-id="6d640-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6d640-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d640-104">Description</span></span>  
 <span data-ttu-id="6d640-105">Numero di operazioni transazionali interrotte in questo servizio in un secondo.</span><span class="sxs-lookup"><span data-stu-id="6d640-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="6d640-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="6d640-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6d640-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6d640-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
