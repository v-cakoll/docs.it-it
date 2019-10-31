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
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127954"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b61d6-102">Metodo ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="b61d6-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b61d6-103">Ottiene un valore che indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="b61d6-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b61d6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b61d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b61d6-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b61d6-106">[out] `true` se il modulo è dinamico; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b61d6-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b61d6-107">Note</span><span class="sxs-lookup"><span data-stu-id="b61d6-107">Remarks</span></span>  
 <span data-ttu-id="b61d6-108">Un modulo dinamico può aggiungere nuove classi ed eliminare le classi esistenti anche dopo il caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="b61d6-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b61d6-109">I callback [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) indicano al debugger quando una classe è stata aggiunta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="b61d6-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b61d6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b61d6-110">Requirements</span></span>  
 <span data-ttu-id="b61d6-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b61d6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b61d6-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b61d6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b61d6-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b61d6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b61d6-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b61d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
