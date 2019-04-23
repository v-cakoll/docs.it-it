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
ms.openlocfilehash: ea1c1f998febccbc80fb10cef5a8dfd229e1987e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095945"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="2d145-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="2d145-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="2d145-103">Ottiene la quantità di spazio dello stack che viene garantito come disponibile dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="2d145-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d145-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d145-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d145-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d145-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="2d145-106">[out] Puntatore al numero di byte che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="2d145-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d145-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d145-107">Requirements</span></span>  
 <span data-ttu-id="2d145-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d145-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d145-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d145-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d145-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2d145-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d145-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d145-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d145-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d145-112">See also</span></span>

- [<span data-ttu-id="2d145-113">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2d145-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
