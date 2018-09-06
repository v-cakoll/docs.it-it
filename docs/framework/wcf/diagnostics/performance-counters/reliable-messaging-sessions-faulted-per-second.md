---
title: Sessioni di messaggistica affidabile con errori per secondo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873991"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="7f024-102">Sessioni di messaggistica affidabile con errori per secondo</span><span class="sxs-lookup"><span data-stu-id="7f024-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="7f024-103">Nome contatore: sessioni di messaggistica affidabile con errori al secondo.</span><span class="sxs-lookup"><span data-stu-id="7f024-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7f024-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f024-104">Description</span></span>  
 <span data-ttu-id="7f024-105">Numero di sessioni di messaggistica affidabile con errori per il servizio in un secondo.</span><span class="sxs-lookup"><span data-stu-id="7f024-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="7f024-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="7f024-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7f024-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7f024-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
