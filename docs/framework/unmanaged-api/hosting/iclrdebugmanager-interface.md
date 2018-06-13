---
title: Interfaccia ICLRDebugManager
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d123177bf9f1b5eee1a2ba4d9b7f2042ddc07aa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434939"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="534fe-102">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="534fe-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="534fe-103">Fornisce metodi che consentono a un host associare un set di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="534fe-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="534fe-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="534fe-104">Methods</span></span>  
  
|<span data-ttu-id="534fe-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="534fe-105">Method</span></span>|<span data-ttu-id="534fe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="534fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="534fe-107">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="534fe-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="534fe-108">Stabilisce una nuova connessione tra l'host e il debugger per associare attività a un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="534fe-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="534fe-109">Metodo EndConnection</span><span class="sxs-lookup"><span data-stu-id="534fe-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="534fe-110">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="534fe-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="534fe-111">Metodo GetDacl</span><span class="sxs-lookup"><span data-stu-id="534fe-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="534fe-112">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="534fe-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="534fe-113">Metodo IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="534fe-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="534fe-114">Ottiene un valore che indica se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="534fe-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="534fe-115">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="534fe-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="534fe-116">Associa un elenco di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanze con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="534fe-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="534fe-117">Metodo SetDacl</span><span class="sxs-lookup"><span data-stu-id="534fe-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="534fe-118">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="534fe-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="534fe-119">Metodo SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="534fe-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="534fe-120">Imposta i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="534fe-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="534fe-121">Il criterio determina se le informazioni sui numeri di riga e i file sono incluso in stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="534fe-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="534fe-122">Note</span><span class="sxs-lookup"><span data-stu-id="534fe-122">Remarks</span></span>  
 <span data-ttu-id="534fe-123">Negli scenari di debug, potrebbe essere un host per raggruppare le attività in base alla propria logica di programmazione.</span><span class="sxs-lookup"><span data-stu-id="534fe-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="534fe-124">Ad esempio, un raggruppamento consentirebbe a uno sviluppatore visualizzare solo le attività richieste dalle API dello sviluppatore, anziché visualizzare ogni attività in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="534fe-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="534fe-125">`ICLRDebugManager` consente all'host implementare questo tipo di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="534fe-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="534fe-126">Tre `ICLRDebugManager` metodi, `BeginConnection`, `SetConnectionTasks` e `EndConnection`, variano in base alla loro.</span><span class="sxs-lookup"><span data-stu-id="534fe-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="534fe-127">Devono essere chiamati nell'ordine indicato a funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="534fe-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="534fe-128">Il raggruppamento e gli identificatori e nomi descrittivi che l'host viene assegnato al raggruppamento, non hanno alcun significato per common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="534fe-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="534fe-129">CLR passa semplicemente le informazioni insieme al debugger.</span><span class="sxs-lookup"><span data-stu-id="534fe-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534fe-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="534fe-130">Requirements</span></span>  
 <span data-ttu-id="534fe-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534fe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534fe-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="534fe-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="534fe-133">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="534fe-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="534fe-134">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534fe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534fe-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="534fe-135">See Also</span></span>  
 [<span data-ttu-id="534fe-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="534fe-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
