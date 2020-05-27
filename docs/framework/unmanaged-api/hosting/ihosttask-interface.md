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
ms.openlocfilehash: f8f476f681764a46700dd5ec83c8f9b2739f18f6
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842491"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="62307-102">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="62307-102">IHostTask Interface</span></span>
<span data-ttu-id="62307-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di comunicare con l'host per gestire le attività.</span><span class="sxs-lookup"><span data-stu-id="62307-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62307-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="62307-104">Methods</span></span>  
  
|<span data-ttu-id="62307-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="62307-105">Method</span></span>|<span data-ttu-id="62307-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62307-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62307-107">Metodo Alert</span><span class="sxs-lookup"><span data-stu-id="62307-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="62307-108">Richiede che l'host risvegli l'attività rappresentata dall' `IHostTask` istanza corrente, in modo che l'attività possa essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="62307-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="62307-109">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="62307-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="62307-110">Ottiene il livello di priorità del thread dell'attività rappresentata dall' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="62307-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="62307-111">Metodo join</span><span class="sxs-lookup"><span data-stu-id="62307-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="62307-112">Blocca l'attività chiamante fino a quando l'attività rappresentata dall'istanza corrente non `IHostTask` viene completata, l'intervallo di tempo specificato scade oppure [IHostTask:: Alert](ihosttask-alert-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="62307-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="62307-113">Metodo SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="62307-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="62307-114">Associa un'istanza dell' [interfaccia ICLRTask](iclrtask-interface.md) all' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="62307-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="62307-115">Metodo SetPriority</span><span class="sxs-lookup"><span data-stu-id="62307-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="62307-116">Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="62307-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="62307-117">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="62307-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="62307-118">Richiede che l'host sposti l'attività rappresentata dall' `IHostTask` istanza corrente da uno stato sospeso a uno stato attivo, in cui è possibile eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="62307-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62307-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="62307-119">Remarks</span></span>  
 <span data-ttu-id="62307-120">CLR chiama i metodi definiti da `IHostTask` per avviare un'attività, impostare il livello di priorità del thread e così via.</span><span class="sxs-lookup"><span data-stu-id="62307-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62307-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62307-121">Requirements</span></span>  
 <span data-ttu-id="62307-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62307-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62307-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62307-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62307-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62307-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62307-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62307-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62307-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62307-126">See also</span></span>

- [<span data-ttu-id="62307-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="62307-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="62307-128">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="62307-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="62307-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="62307-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="62307-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="62307-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
