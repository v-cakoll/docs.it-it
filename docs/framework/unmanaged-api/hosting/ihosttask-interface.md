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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121385"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="6697c-102">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6697c-102">IHostTask Interface</span></span>
<span data-ttu-id="6697c-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di comunicare con l'host per gestire le attività.</span><span class="sxs-lookup"><span data-stu-id="6697c-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6697c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6697c-104">Methods</span></span>  
  
|<span data-ttu-id="6697c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6697c-105">Method</span></span>|<span data-ttu-id="6697c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6697c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6697c-107">Metodo Alert</span><span class="sxs-lookup"><span data-stu-id="6697c-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="6697c-108">Richiede che l'host risvegli l'attività rappresentata dall'istanza di `IHostTask` corrente, in modo che l'attività possa essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="6697c-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="6697c-109">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="6697c-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="6697c-110">Ottiene il livello di priorità del thread dell'attività rappresentata dall'istanza di `IHostTask` corrente.</span><span class="sxs-lookup"><span data-stu-id="6697c-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6697c-111">Metodo join</span><span class="sxs-lookup"><span data-stu-id="6697c-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="6697c-112">Blocca l'attività chiamante finché non viene completata l'attività rappresentata dall'istanza di `IHostTask` corrente, l'intervallo di tempo specificato scade oppure viene chiamato [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6697c-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="6697c-113">Metodo SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="6697c-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="6697c-114">Associa un'istanza di [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) all'istanza di `IHostTask` corrente.</span><span class="sxs-lookup"><span data-stu-id="6697c-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6697c-115">Metodo SetPriority</span><span class="sxs-lookup"><span data-stu-id="6697c-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="6697c-116">Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall'istanza di `IHostTask` corrente.</span><span class="sxs-lookup"><span data-stu-id="6697c-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6697c-117">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="6697c-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="6697c-118">Richiede che l'host sposti l'attività rappresentata dall'istanza corrente di `IHostTask` da uno stato sospeso a uno stato attivo, in cui è possibile eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="6697c-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6697c-119">Note</span><span class="sxs-lookup"><span data-stu-id="6697c-119">Remarks</span></span>  
 <span data-ttu-id="6697c-120">CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare il livello di priorità del thread e così via.</span><span class="sxs-lookup"><span data-stu-id="6697c-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6697c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6697c-121">Requirements</span></span>  
 <span data-ttu-id="6697c-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6697c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6697c-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6697c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6697c-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6697c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6697c-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6697c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6697c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6697c-126">See also</span></span>

- [<span data-ttu-id="6697c-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6697c-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6697c-128">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6697c-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6697c-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6697c-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="6697c-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6697c-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
