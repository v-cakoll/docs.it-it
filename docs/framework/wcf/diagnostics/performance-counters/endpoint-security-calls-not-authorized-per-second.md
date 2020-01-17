---
title: 'Endpoint: chiamate di sicurezza non autorizzate al secondo'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 8c287ef4c156bb0a76a4b1d08b0d70b40bd76229
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163176"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="de551-102">Endpoint: chiamate di sicurezza non autorizzate al secondo</span><span class="sxs-lookup"><span data-stu-id="de551-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="de551-103">Nome contatore: chiamate di sicurezza non autorizzate al secondo.</span><span class="sxs-lookup"><span data-stu-id="de551-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="de551-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de551-104">Description</span></span>  
 <span data-ttu-id="de551-105">Numero di messaggi in ingresso al secondo provenienti da un utente valido e adeguatamente protetti, ma per cui l'utente non è autorizzato a eseguire attività specifiche.</span><span class="sxs-lookup"><span data-stu-id="de551-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="de551-106">Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="de551-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="de551-107">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="de551-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="de551-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="de551-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
