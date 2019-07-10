---
title: Metodo IHostTaskManager::GetStackGuarantee
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 739670fb84eb0145fd8bf8073f453518487c38b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749579"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="5abd7-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="5abd7-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="5abd7-103">Ottiene la quantità di spazio dello stack che viene garantito come disponibile dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="5abd7-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5abd7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5abd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5abd7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5abd7-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="5abd7-106">[out] Puntatore al numero di byte che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="5abd7-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5abd7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5abd7-107">Requirements</span></span>  
 <span data-ttu-id="5abd7-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5abd7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5abd7-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5abd7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5abd7-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5abd7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5abd7-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5abd7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abd7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5abd7-112">See also</span></span>

- [<span data-ttu-id="5abd7-113">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5abd7-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
