---
title: 'Servizio: chiamate di sicurezza non autorizzate al secondo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 964eff97a58ab7d5a68dbc1891473ae8d04a50ad
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163878"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="a5439-102">Servizio: chiamate di sicurezza non autorizzate al secondo</span><span class="sxs-lookup"><span data-stu-id="a5439-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="a5439-103">Nome contatore: chiamate di sicurezza non autorizzate al secondo</span><span class="sxs-lookup"><span data-stu-id="a5439-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="a5439-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5439-104">Description</span></span>  
 <span data-ttu-id="a5439-105">Numero di messaggi in ingresso al secondo provenienti da un utente valido e adeguatamente protetti, ma per cui l'utente non è autorizzato a eseguire attività specifiche.</span><span class="sxs-lookup"><span data-stu-id="a5439-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="a5439-106">Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="a5439-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="a5439-107">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="a5439-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a5439-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a5439-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
