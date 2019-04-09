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
ms.openlocfilehash: 77a2ccaf6f972fadd8396378dc7777ec4c85120d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110227"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="d8d7e-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="d8d7e-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="d8d7e-103">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="d8d7e-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8d7e-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8d7e-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="d8d7e-106">[in] Puntatore alla funzione da eseguire all'interno dell'apartment.</span><span class="sxs-lookup"><span data-stu-id="d8d7e-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="d8d7e-107">[in] Un puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="d8d7e-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d7e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8d7e-108">Requirements</span></span>  
 <span data-ttu-id="d8d7e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d7e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d7e-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8d7e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8d7e-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d8d7e-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d8d7e-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d8d7e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8d7e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d7e-113">See also</span></span>

- [<span data-ttu-id="d8d7e-114">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="d8d7e-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
