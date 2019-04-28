---
title: 'Endpoint: Transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916253"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="da610-102">Endpoint: Transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="da610-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="da610-103">Nome contatore: Transazioni propagate al secondo.</span><span class="sxs-lookup"><span data-stu-id="da610-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="da610-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da610-104">Description</span></span>  
 <span data-ttu-id="da610-105">Numero di transazioni propagate alle operazioni per l'endpoint al secondo.</span><span class="sxs-lookup"><span data-stu-id="da610-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="da610-106">Questo contatore viene incrementato ogni volta che è presente un ID di transazione nel messaggio inviato all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="da610-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="da610-107">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="da610-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="da610-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="da610-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
