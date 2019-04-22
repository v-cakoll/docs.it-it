---
title: Interfaccia IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081502"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="1910d-102">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="1910d-102">IHostTask Interface</span></span>
<span data-ttu-id="1910d-103">Fornisce metodi che consentono di common language runtime (CLR) per comunicare con l'host per gestire le attività.</span><span class="sxs-lookup"><span data-stu-id="1910d-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1910d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1910d-104">Methods</span></span>  
  
|<span data-ttu-id="1910d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1910d-105">Method</span></span>|<span data-ttu-id="1910d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1910d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1910d-107">Metodo Alert</span><span class="sxs-lookup"><span data-stu-id="1910d-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="1910d-108">Richiede che l'host di riattivare l'attività rappresentata dall'oggetto corrente `IHostTask` dell'istanza, in modo che l'attività può essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="1910d-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="1910d-109">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="1910d-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="1910d-110">Ottiene il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="1910d-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1910d-111">Metodo join</span><span class="sxs-lookup"><span data-stu-id="1910d-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="1910d-112">Blocca l'attività chiamante fino a quando l'attività rappresentata dall'oggetto corrente `IHostTask` completamento dell'istanza, è trascorso l'intervallo di tempo specificato, oppure [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="1910d-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="1910d-113">Metodo SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="1910d-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="1910d-114">Associa un' [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza con l'attuale `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="1910d-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1910d-115">Metodo SetPriority</span><span class="sxs-lookup"><span data-stu-id="1910d-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="1910d-116">Il livello di richiede che l'host di modificare la priorità del thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="1910d-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1910d-117">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="1910d-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="1910d-118">Richiede che l'host di spostare l'attività rappresentata dall'oggetto corrente `IHostTask` istanza da uno stato sospeso in uno stato in tempo reale, in cui è possibile eseguire codice.</span><span class="sxs-lookup"><span data-stu-id="1910d-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1910d-119">Note</span><span class="sxs-lookup"><span data-stu-id="1910d-119">Remarks</span></span>  
 <span data-ttu-id="1910d-120">CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare la priorità di thread livello, e così via.</span><span class="sxs-lookup"><span data-stu-id="1910d-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1910d-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1910d-121">Requirements</span></span>  
 <span data-ttu-id="1910d-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1910d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1910d-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1910d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1910d-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1910d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1910d-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1910d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1910d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1910d-126">See also</span></span>

- [<span data-ttu-id="1910d-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1910d-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1910d-128">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1910d-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1910d-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1910d-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="1910d-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1910d-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
