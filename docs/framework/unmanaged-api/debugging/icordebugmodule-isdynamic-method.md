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
ms.openlocfilehash: 5157c62f2719a9d62608750cd122561807197494
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418297"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b008b-102">Metodo ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="b008b-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b008b-103">Ottiene un valore che indica se questo modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="b008b-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b008b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b008b-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b008b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b008b-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b008b-106">[out] `true` se questo modulo è dinamico; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b008b-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b008b-107">Note</span><span class="sxs-lookup"><span data-stu-id="b008b-107">Remarks</span></span>  
 <span data-ttu-id="b008b-108">Un modulo dinamico può aggiungere nuove classi ed eliminare classi esistenti, anche dopo che è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="b008b-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b008b-109">Il [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callback informano il debugger quando una classe è stato aggiunta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="b008b-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b008b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b008b-110">Requirements</span></span>  
 <span data-ttu-id="b008b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b008b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b008b-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b008b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b008b-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b008b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b008b-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b008b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
