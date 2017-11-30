---
title: Interfaccia ICLRTaskManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3144338ddce262aaa6772f588a4f1a652cc57e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="0960c-102">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0960c-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="0960c-103">Fornisce metodi che consentono all'host per richiedere in modo esplicito che common language runtime (CLR) di creano una nuova attività, ottenere l'attività attualmente in esecuzione e impostare la lingua geografica per l'attività.</span><span class="sxs-lookup"><span data-stu-id="0960c-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0960c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0960c-104">Methods</span></span>  
  
|<span data-ttu-id="0960c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0960c-105">Method</span></span>|<span data-ttu-id="0960c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0960c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0960c-107">CreateTask (metodo)</span><span class="sxs-lookup"><span data-stu-id="0960c-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="0960c-108">Le richieste in modo esplicito a CLR di creare un nuovo [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="0960c-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="0960c-109">GetCurrentTask (metodo)</span><span class="sxs-lookup"><span data-stu-id="0960c-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="0960c-110">Ottiene il `ICLRTask` istanza che rappresenta l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0960c-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="0960c-111">GetCurrentTaskType (metodo)</span><span class="sxs-lookup"><span data-stu-id="0960c-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="0960c-112">Ottiene il tipo di attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0960c-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="0960c-113">SetLocale (metodo)</span><span class="sxs-lookup"><span data-stu-id="0960c-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="0960c-114">Notifica a Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali per l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0960c-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="0960c-115">SetUILocale (metodo)</span><span class="sxs-lookup"><span data-stu-id="0960c-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="0960c-116">Notifica a common language runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente per l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0960c-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0960c-117">Note</span><span class="sxs-lookup"><span data-stu-id="0960c-117">Remarks</span></span>  
 <span data-ttu-id="0960c-118">Ogni attività che è in esecuzione in un ambiente host dispone di rappresentazioni sia sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="0960c-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="0960c-119">L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per assicurare una corretta comunicazione tra l'host e il CLR riguardanti l'attività.</span><span class="sxs-lookup"><span data-stu-id="0960c-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="0960c-120">I due oggetti devono essere creati e creare un'istanza prima di eseguire codice gestito in un thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0960c-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0960c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0960c-121">Requirements</span></span>  
 <span data-ttu-id="0960c-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0960c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0960c-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0960c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0960c-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0960c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0960c-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0960c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0960c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0960c-126">See Also</span></span>  
 [<span data-ttu-id="0960c-127">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0960c-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0960c-128">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0960c-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0960c-129">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0960c-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="0960c-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0960c-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
