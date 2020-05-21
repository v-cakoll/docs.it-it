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
ms.openlocfilehash: 9e26071181e8e0712c753fa03d5e16eb85e5ee68
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762832"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="21803-102">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="21803-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="21803-103">Fornisce metodi che consentono all'host di richiedere in modo esplicito che il Common Language Runtime (CLR) crei una nuova attività, ottenga l'attività attualmente in esecuzione e imposta la lingua geografica e le impostazioni cultura per l'attività.</span><span class="sxs-lookup"><span data-stu-id="21803-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21803-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="21803-104">Methods</span></span>  
  
|<span data-ttu-id="21803-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="21803-105">Method</span></span>|<span data-ttu-id="21803-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21803-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21803-107">Metodo CreateTask</span><span class="sxs-lookup"><span data-stu-id="21803-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="21803-108">Richiede in modo esplicito che CLR crei una nuova istanza di [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="21803-108">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="21803-109">Metodo GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="21803-109">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="21803-110">Ottiene l' `ICLRTask` istanza di che rappresenta l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21803-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="21803-111">Metodo GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="21803-111">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="21803-112">Ottiene il tipo dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21803-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="21803-113">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="21803-113">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="21803-114">Notifica a CLR che l'host ha modificato l'identificatore delle impostazioni locali nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21803-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="21803-115">Metodo SetUILocale</span><span class="sxs-lookup"><span data-stu-id="21803-115">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="21803-116">Notifica all'Common Language Runtime che l'host ha modificato l'identificatore delle impostazioni locali dell'interfaccia utente nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21803-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21803-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="21803-117">Remarks</span></span>  
 <span data-ttu-id="21803-118">Ogni attività in esecuzione in un ambiente ospitato dispone di rappresentazioni sul lato host (un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) e sul lato CLR (un'istanza di [ICLRTask](iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="21803-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="21803-119">L'host o CLR può avviare la creazione di un'attività, ma la rappresentazione sul lato host deve essere associata a una rappresentazione sul lato CLR corrispondente per garantire la corretta comunicazione tra l'host e CLR in relazione all'attività.</span><span class="sxs-lookup"><span data-stu-id="21803-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="21803-120">È necessario creare e creare un'istanza dei due oggetti prima che il codice gestito possa essere eseguito su un thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21803-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21803-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21803-121">Requirements</span></span>  
 <span data-ttu-id="21803-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21803-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21803-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21803-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21803-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21803-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21803-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21803-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21803-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21803-126">See also</span></span>

- [<span data-ttu-id="21803-127">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="21803-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="21803-128">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="21803-128">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="21803-129">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="21803-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="21803-130">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="21803-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
