---
title: Metodo ICLRTaskManager::GetCurrentTaskType
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 595c39b56587150d0d8f9c3f8bdfcae4c075e4d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770169"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="a03ab-102">Metodo ICLRTaskManager::GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="a03ab-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="a03ab-103">Ottiene il tipo dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a03ab-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a03ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a03ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a03ab-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="a03ab-106">[out] Un puntatore a un valore di [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumerazione che indica il tipo di attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a03ab-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a03ab-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a03ab-107">Requirements</span></span>  
 <span data-ttu-id="a03ab-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a03ab-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03ab-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a03ab-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a03ab-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a03ab-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a03ab-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03ab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03ab-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a03ab-112">See also</span></span>

- [<span data-ttu-id="a03ab-113">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a03ab-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
