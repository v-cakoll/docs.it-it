---
title: Contatori delle prestazioni per l'operazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 83460e1c4db17938466051269dbeba3f19e0b40a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="operation-performance-counters"></a><span data-ttu-id="e2a9a-102">Contatori delle prestazioni per l'operazione</span><span class="sxs-lookup"><span data-stu-id="e2a9a-102">Operation Performance Counters</span></span>
<span data-ttu-id="e2a9a-103">I contatori delle prestazioni per l'operazione si trovano nell'oggetto prestazione `ServiceModelOperation 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="e2a9a-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="e2a9a-104">Ogni operazione ha un'istanza singola.</span><span class="sxs-lookup"><span data-stu-id="e2a9a-104">Each operation has an individual instance.</span></span> <span data-ttu-id="e2a9a-105">Ovvero, se un determinato contratto ha 10 operazioni, ad esso sono associate 10 istanze di contatore per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e2a9a-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="e2a9a-106">Le istanze di oggetti vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="e2a9a-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="e2a9a-107">Questo contatore consente di misurare come viene usata la chiamata e le prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e2a9a-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e2a9a-108">Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e2a9a-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="e2a9a-109">Quando il nome dell'istanza di un contatore [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la lunghezza massima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] sostituisce una parte del nome dell'istanza con un valore hash.</span><span class="sxs-lookup"><span data-stu-id="e2a9a-109">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a9a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a9a-110">See Also</span></span>  
 [<span data-ttu-id="e2a9a-111">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e2a9a-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
