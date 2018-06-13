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
ms.openlocfilehash: 089aaf96a164be7eaa258dec65807bd75c998eb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440970"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="86664-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="86664-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="86664-103">Ottiene la quantità di spazio dello stack è garantito che siano disponibili dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="86664-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86664-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86664-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86664-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86664-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="86664-106">[out] Puntatore al numero di byte che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="86664-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86664-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86664-107">Requirements</span></span>  
 <span data-ttu-id="86664-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86664-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86664-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="86664-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86664-110">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="86664-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86664-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86664-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86664-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86664-112">See Also</span></span>  
 [<span data-ttu-id="86664-113">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="86664-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
