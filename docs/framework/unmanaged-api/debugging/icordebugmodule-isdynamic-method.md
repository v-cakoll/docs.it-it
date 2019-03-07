---
title: Metodo ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8012d669cabc1bb589dcfe66bdf2e9b83dc5cb2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502449"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="552c2-102">Metodo ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="552c2-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="552c2-103">Ottiene un valore che indica se questo modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="552c2-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="552c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="552c2-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="552c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="552c2-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="552c2-106">[out] `true` se questo modulo è dinamica; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="552c2-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="552c2-107">Note</span><span class="sxs-lookup"><span data-stu-id="552c2-107">Remarks</span></span>  
 <span data-ttu-id="552c2-108">Un modulo dinamico è possibile aggiungere nuove classi ed eliminare le classi esistenti anche dopo che il modulo è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="552c2-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="552c2-109">Il [LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callback informano il debugger quando una classe è stato aggiunta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="552c2-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="552c2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="552c2-110">Requirements</span></span>  
 <span data-ttu-id="552c2-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="552c2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="552c2-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="552c2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="552c2-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="552c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="552c2-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="552c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
