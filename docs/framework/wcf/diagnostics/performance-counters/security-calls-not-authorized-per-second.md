---
title: Chiamate di sicurezza non autorizzate al secondo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 73500901b89eb2cb61fe34895ce6ba150b7e3357
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="247a7-102">Chiamate di sicurezza non autorizzate al secondo</span><span class="sxs-lookup"><span data-stu-id="247a7-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="247a7-103">Nome contatore: chiamate di sicurezza non autorizzate al secondo.</span><span class="sxs-lookup"><span data-stu-id="247a7-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="247a7-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="247a7-104">Description</span></span>  
 <span data-ttu-id="247a7-105">Numero di chiamate non autorizzate per l'operazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="247a7-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="247a7-106">Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="247a7-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="247a7-107">Indica che il messaggio in ingresso proviene da un utente valido ed è adeguatamente protetto, ma l'utente non è autorizzato a eseguire attività specifiche.</span><span class="sxs-lookup"><span data-stu-id="247a7-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="247a7-108">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="247a7-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="247a7-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="247a7-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
