---
title: Interfaccia ICLRTaskManager
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763373"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="fcaa6-102">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fcaa6-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="fcaa6-103">Fornisce metodi che consentono all'host per richiedere in modo esplicito che common language runtime (CLR) creare una nuova attività, ottenere l'attività attualmente in esecuzione e impostare il linguaggio geografica e le impostazioni cultura per l'attività.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcaa6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fcaa6-104">Methods</span></span>  
  
|<span data-ttu-id="fcaa6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fcaa6-105">Method</span></span>|<span data-ttu-id="fcaa6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcaa6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcaa6-107">Metodo CreateTask</span><span class="sxs-lookup"><span data-stu-id="fcaa6-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="fcaa6-108">Le richieste in modo esplicito a CLR di creare una nuova [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="fcaa6-109">Metodo GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="fcaa6-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="fcaa6-110">Ottiene il `ICLRTask` istanza che rappresenta l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="fcaa6-111">Metodo GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="fcaa6-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="fcaa6-112">Ottiene il tipo dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="fcaa6-113">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="fcaa6-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="fcaa6-114">Notifica CLR che l'host ha modificato l'identificatore delle impostazioni locali dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="fcaa6-115">Metodo SetUILocale</span><span class="sxs-lookup"><span data-stu-id="fcaa6-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="fcaa6-116">Notifica di common language runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcaa6-117">Note</span><span class="sxs-lookup"><span data-stu-id="fcaa6-117">Remarks</span></span>  
 <span data-ttu-id="fcaa6-118">Ogni attività è in esecuzione in un ambiente ospitato dispone di rappresentazioni sia sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="fcaa6-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="fcaa6-119">L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione lato host deve essere associata a una rappresentazione lato CLR corrispondente per garantire la corretta comunicazione tra l'host e il CLR riguardanti l'attività.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="fcaa6-120">I due oggetti devono essere creati e creare un'istanza prima di eseguire codice gestito in un thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fcaa6-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcaa6-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcaa6-121">Requirements</span></span>  
 <span data-ttu-id="fcaa6-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcaa6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaa6-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fcaa6-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcaa6-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fcaa6-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcaa6-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcaa6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcaa6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcaa6-126">See also</span></span>

- [<span data-ttu-id="fcaa6-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fcaa6-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fcaa6-128">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="fcaa6-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fcaa6-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fcaa6-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="fcaa6-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="fcaa6-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
