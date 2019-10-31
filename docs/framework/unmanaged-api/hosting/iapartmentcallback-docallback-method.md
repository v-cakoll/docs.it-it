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
ms.openlocfilehash: 9bb257a3d84d5022b9ae13c89a34572485d3033b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126950"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="72254-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="72254-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="72254-103">Esegue la funzione specificata in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="72254-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72254-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72254-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72254-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72254-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="72254-106">in Puntatore alla funzione da eseguire all'interno dell'Apartment.</span><span class="sxs-lookup"><span data-stu-id="72254-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="72254-107">in Puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="72254-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72254-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72254-108">Requirements</span></span>  
 <span data-ttu-id="72254-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72254-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72254-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="72254-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72254-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="72254-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72254-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72254-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72254-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72254-113">See also</span></span>

- [<span data-ttu-id="72254-114">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="72254-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
