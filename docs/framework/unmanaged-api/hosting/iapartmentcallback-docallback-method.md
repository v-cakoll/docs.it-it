---
title: Metodo IApartmentCallback::DoCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback.DoCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06aaab6d4ad7d33bbdc52a38c999cc925eee1666
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="8463e-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="8463e-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="8463e-103">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="8463e-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8463e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8463e-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8463e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8463e-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="8463e-106">[in] Puntatore alla funzione da eseguire all'interno di apartment.</span><span class="sxs-lookup"><span data-stu-id="8463e-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="8463e-107">[in] Puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="8463e-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8463e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8463e-108">Requirements</span></span>  
 <span data-ttu-id="8463e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8463e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8463e-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8463e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8463e-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8463e-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8463e-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8463e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8463e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8463e-113">See Also</span></span>  
 [<span data-ttu-id="8463e-114">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="8463e-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
