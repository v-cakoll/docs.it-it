---
title: Metodo IApartmentCallback::DoCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80aa64a8867a84100996ae88c5e65233d6b15782
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481066"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="a3540-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="a3540-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="a3540-103">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="a3540-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3540-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3540-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3540-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3540-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="a3540-106">[in] Puntatore alla funzione da eseguire all'interno dell'apartment.</span><span class="sxs-lookup"><span data-stu-id="a3540-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="a3540-107">[in] Un puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="a3540-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3540-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3540-108">Requirements</span></span>  
 <span data-ttu-id="a3540-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3540-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3540-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3540-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3540-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a3540-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3540-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3540-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3540-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3540-113">See also</span></span>
- [<span data-ttu-id="a3540-114">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="a3540-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
