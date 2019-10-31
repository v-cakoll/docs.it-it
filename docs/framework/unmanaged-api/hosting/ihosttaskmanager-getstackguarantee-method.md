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
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133031"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="e892d-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="e892d-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="e892d-103">Ottiene la quantità di spazio dello stack che è garantita come disponibile al termine di un'operazione dello stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="e892d-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e892d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e892d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e892d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e892d-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="e892d-106">out Puntatore al numero di byte disponibili.</span><span class="sxs-lookup"><span data-stu-id="e892d-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e892d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e892d-107">Requirements</span></span>  
 <span data-ttu-id="e892d-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e892d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e892d-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e892d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e892d-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e892d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e892d-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e892d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e892d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e892d-112">See also</span></span>

- [<span data-ttu-id="e892d-113">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e892d-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
