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
ms.openlocfilehash: 1a56c3ebe4b1c528f9c6555bdfbf1270a438410d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617113"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="2ad66-102">Metodo IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="2ad66-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="2ad66-103">Esegue la funzione specificata in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="2ad66-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ad66-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad66-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ad66-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="2ad66-106">in Puntatore alla funzione da eseguire all'interno dell'Apartment.</span><span class="sxs-lookup"><span data-stu-id="2ad66-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="2ad66-107">in Puntatore all'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="2ad66-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad66-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ad66-108">Requirements</span></span>  
 <span data-ttu-id="2ad66-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad66-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad66-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2ad66-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ad66-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ad66-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ad66-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad66-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad66-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ad66-113">See also</span></span>

- [<span data-ttu-id="2ad66-114">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="2ad66-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
