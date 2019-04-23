---
title: Metodo IHostTask::Start
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d45c5b09358430535438734b38e5dce5d1bcdd3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101627"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="eba82-102">Metodo IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="eba82-102">IHostTask::Start Method</span></span>
<span data-ttu-id="eba82-103">Richiede che l'host di spostare l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza da stato di sospensione a uno stato in tempo reale, in cui è possibile eseguire codice.</span><span class="sxs-lookup"><span data-stu-id="eba82-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eba82-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="eba82-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eba82-105">Return Value</span></span>  
  
|<span data-ttu-id="eba82-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eba82-106">HRESULT</span></span>|<span data-ttu-id="eba82-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eba82-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eba82-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="eba82-108">S_OK</span></span>|<span data-ttu-id="eba82-109">Avvio eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="eba82-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="eba82-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eba82-110">E_FAIL</span></span>|<span data-ttu-id="eba82-111">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="eba82-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eba82-112">Quando viene restituito un metodo di E_FAIL, common language runtime (CLR) non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="eba82-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="eba82-113">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eba82-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eba82-114">Note</span><span class="sxs-lookup"><span data-stu-id="eba82-114">Remarks</span></span>  
 <span data-ttu-id="eba82-115">`Start` Restituisce sempre un valore HRESULT S_OK, tranne nei casi in cui si è verificato un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="eba82-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eba82-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eba82-116">Requirements</span></span>  
 <span data-ttu-id="eba82-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eba82-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eba82-118">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eba82-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eba82-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eba82-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eba82-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eba82-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba82-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eba82-121">See also</span></span>

- [<span data-ttu-id="eba82-122">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="eba82-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="eba82-123">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="eba82-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="eba82-124">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="eba82-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="eba82-125">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="eba82-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
