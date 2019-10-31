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
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092192"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="51738-102">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="51738-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="51738-103">Fornisce metodi che consentono all'host di richiedere in modo esplicito che il Common Language Runtime (CLR) crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposta la lingua geografica e le impostazioni cultura per l'attività.</span><span class="sxs-lookup"><span data-stu-id="51738-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51738-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="51738-104">Methods</span></span>  
  
|<span data-ttu-id="51738-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="51738-105">Method</span></span>|<span data-ttu-id="51738-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51738-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51738-107">Metodo CreateTask</span><span class="sxs-lookup"><span data-stu-id="51738-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="51738-108">Richiede in modo esplicito che CLR crei una nuova istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="51738-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="51738-109">Metodo GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="51738-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="51738-110">Ottiene l'istanza `ICLRTask` che rappresenta l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51738-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="51738-111">Metodo GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="51738-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="51738-112">Ottiene il tipo dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51738-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="51738-113">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="51738-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="51738-114">Notifica a CLR che l'host ha modificato l'identificatore delle impostazioni locali nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51738-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="51738-115">Metodo SetUILocale</span><span class="sxs-lookup"><span data-stu-id="51738-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="51738-116">Notifica all'Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51738-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51738-117">Note</span><span class="sxs-lookup"><span data-stu-id="51738-117">Remarks</span></span>  
 <span data-ttu-id="51738-118">Ogni attività in esecuzione in un ambiente ospitato dispone di rappresentazioni sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="51738-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="51738-119">L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione sul lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per garantire la corretta comunicazione tra l'host e CLR in relazione all'attività.</span><span class="sxs-lookup"><span data-stu-id="51738-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="51738-120">È necessario creare e creare un'istanza dei due oggetti prima che il codice gestito possa essere eseguito su un thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="51738-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51738-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51738-121">Requirements</span></span>  
 <span data-ttu-id="51738-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51738-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51738-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51738-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51738-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51738-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51738-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51738-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51738-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51738-126">See also</span></span>

- [<span data-ttu-id="51738-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="51738-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="51738-128">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="51738-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="51738-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="51738-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="51738-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="51738-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
