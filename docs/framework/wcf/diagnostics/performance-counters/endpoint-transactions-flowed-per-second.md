---
title: 'Endpoint: transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264363"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="73810-102">Endpoint: transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="73810-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="73810-103">Nome contatore: transazioni propagate al secondo.</span><span class="sxs-lookup"><span data-stu-id="73810-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="73810-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73810-104">Description</span></span>  
 <span data-ttu-id="73810-105">Numero di transazioni propagate alle operazioni per l'endpoint al secondo.</span><span class="sxs-lookup"><span data-stu-id="73810-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="73810-106">Questo contatore viene incrementato ogni volta che è presente un ID di transazione nel messaggio inviato all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="73810-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="73810-107">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="73810-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="73810-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="73810-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
