---
title: Chiamate di sicurezza non autorizzate al secondo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 2986ba241ef9b6c110a4742f77320469cdf5f07a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163930"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="b5618-102">Chiamate di sicurezza non autorizzate al secondo</span><span class="sxs-lookup"><span data-stu-id="b5618-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="b5618-103">Nome contatore: chiamate di sicurezza non autorizzate al secondo.</span><span class="sxs-lookup"><span data-stu-id="b5618-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5618-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5618-104">Description</span></span>  
 <span data-ttu-id="b5618-105">Numero di chiamate non autorizzate per l'operazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="b5618-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="b5618-106">Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="b5618-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="b5618-107">Indica che il messaggio in ingresso proviene da un utente valido ed è adeguatamente protetto, ma l'utente non è autorizzato a eseguire attività specifiche.</span><span class="sxs-lookup"><span data-stu-id="b5618-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="b5618-108">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="b5618-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b5618-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b5618-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
