---
title: Interfaccia ICLRDebugManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e537b955524f2721868ddf5da9fccf68f9d4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="51dab-102">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="51dab-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="51dab-103">Fornisce metodi che consentono a un host associare un set di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="51dab-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51dab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="51dab-104">Methods</span></span>  
  
|<span data-ttu-id="51dab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="51dab-105">Method</span></span>|<span data-ttu-id="51dab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51dab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51dab-107">BeginConnection (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="51dab-108">Stabilisce una nuova connessione tra l'host e il debugger per associare attività a un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="51dab-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="51dab-109">EndConnection (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="51dab-110">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="51dab-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="51dab-111">GetDacl (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="51dab-112">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="51dab-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="51dab-113">IsDebuggerAttached (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="51dab-114">Ottiene un valore che indica se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="51dab-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="51dab-115">SetConnectionTasks (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="51dab-116">Associa un elenco di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanze con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="51dab-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="51dab-117">SetDacl (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="51dab-118">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="51dab-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="51dab-119">SetSymbolReadingPolicy (metodo)</span><span class="sxs-lookup"><span data-stu-id="51dab-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="51dab-120">Imposta i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="51dab-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="51dab-121">Il criterio determina se le informazioni sui numeri di riga e i file sono incluso in stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="51dab-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51dab-122">Note</span><span class="sxs-lookup"><span data-stu-id="51dab-122">Remarks</span></span>  
 <span data-ttu-id="51dab-123">Negli scenari di debug, potrebbe essere un host per raggruppare le attività in base alla propria logica di programmazione.</span><span class="sxs-lookup"><span data-stu-id="51dab-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="51dab-124">Ad esempio, un raggruppamento consentirebbe a uno sviluppatore visualizzare solo le attività richieste dalle API dello sviluppatore, anziché visualizzare ogni attività in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="51dab-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="51dab-125">`ICLRDebugManager`consente all'host implementare questo tipo di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="51dab-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51dab-126">Tre `ICLRDebugManager` metodi, `BeginConnection`, `SetConnectionTasks` e `EndConnection`, variano in base alla loro.</span><span class="sxs-lookup"><span data-stu-id="51dab-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="51dab-127">Devono essere chiamati nell'ordine indicato a funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="51dab-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="51dab-128">Il raggruppamento e gli identificatori e nomi descrittivi che l'host viene assegnato al raggruppamento, non hanno alcun significato per common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="51dab-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="51dab-129">CLR passa semplicemente le informazioni insieme al debugger.</span><span class="sxs-lookup"><span data-stu-id="51dab-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51dab-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51dab-130">Requirements</span></span>  
 <span data-ttu-id="51dab-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51dab-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51dab-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="51dab-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51dab-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51dab-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51dab-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51dab-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51dab-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51dab-135">See Also</span></span>  
 [<span data-ttu-id="51dab-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="51dab-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
