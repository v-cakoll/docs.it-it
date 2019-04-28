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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789494"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="97587-102">Metodo IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="97587-102">IHostTask::Start Method</span></span>
<span data-ttu-id="97587-103">Richiede che l'host di spostare l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza da stato di sospensione a uno stato in tempo reale, in cui è possibile eseguire codice.</span><span class="sxs-lookup"><span data-stu-id="97587-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97587-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97587-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97587-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97587-105">Return Value</span></span>  
  
|<span data-ttu-id="97587-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97587-106">HRESULT</span></span>|<span data-ttu-id="97587-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97587-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97587-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="97587-108">S_OK</span></span>|<span data-ttu-id="97587-109">Avvio eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="97587-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="97587-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97587-110">E_FAIL</span></span>|<span data-ttu-id="97587-111">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="97587-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97587-112">Quando viene restituito un metodo di E_FAIL, common language runtime (CLR) non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="97587-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="97587-113">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="97587-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97587-114">Note</span><span class="sxs-lookup"><span data-stu-id="97587-114">Remarks</span></span>  
 <span data-ttu-id="97587-115">`Start` Restituisce sempre un valore HRESULT S_OK, tranne nei casi in cui si è verificato un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="97587-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97587-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97587-116">Requirements</span></span>  
 <span data-ttu-id="97587-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97587-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97587-118">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97587-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97587-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="97587-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97587-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97587-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97587-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97587-121">See also</span></span>

- [<span data-ttu-id="97587-122">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="97587-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="97587-123">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="97587-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="97587-124">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="97587-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="97587-125">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="97587-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
