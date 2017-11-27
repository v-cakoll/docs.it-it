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
ms.openlocfilehash: 03c72af5fba0871433e46c2b8045c55bbf0a5ff6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="e7541-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="e7541-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="e7541-103">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="e7541-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7541-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7541-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7541-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7541-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="e7541-106">[in] Puntatore alla funzione da eseguire all'interno di apartment.</span><span class="sxs-lookup"><span data-stu-id="e7541-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="e7541-107">[in] Puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="e7541-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7541-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7541-108">Requirements</span></span>  
 <span data-ttu-id="e7541-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7541-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7541-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e7541-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7541-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7541-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7541-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7541-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7541-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7541-113">See Also</span></span>  
 [<span data-ttu-id="e7541-114">IApartmentCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e7541-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
