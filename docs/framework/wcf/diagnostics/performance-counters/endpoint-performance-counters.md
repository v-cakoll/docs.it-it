---
title: Contatori delle prestazioni dell'endpoint
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="2fc1a-102">Contatori delle prestazioni dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="2fc1a-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="2fc1a-103">I contatori delle prestazioni dell'endpoint consentono di raccogliere dati che indicano il livello di efficienza con cui un endpoint accetta i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2fc1a-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="2fc1a-104">Questi contatori si trovano nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` quando si utilizza Performance Monitor per visualizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2fc1a-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="2fc1a-105">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="2fc1a-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="2fc1a-106">I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2fc1a-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2fc1a-107">Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2fc1a-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="2fc1a-108">Quando un nome di istanza dei contatori di Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.</span><span class="sxs-lookup"><span data-stu-id="2fc1a-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc1a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fc1a-109">See Also</span></span>  
 [<span data-ttu-id="2fc1a-110">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="2fc1a-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
