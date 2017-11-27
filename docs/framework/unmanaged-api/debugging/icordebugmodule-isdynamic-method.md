---
title: Metodo ICorDebugModule::IsDynamic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsDynamic
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3583749ddb48015b43d45061d3e4cb10e08016b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="00d9b-102">Metodo ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="00d9b-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="00d9b-103">Ottiene un valore che indica se questo modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="00d9b-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00d9b-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00d9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00d9b-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="00d9b-106">[out] `true` se questo modulo è dinamico; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="00d9b-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00d9b-107">Note</span><span class="sxs-lookup"><span data-stu-id="00d9b-107">Remarks</span></span>  
 <span data-ttu-id="00d9b-108">Un modulo dinamico può aggiungere nuove classi ed eliminare classi esistenti, anche dopo che è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="00d9b-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="00d9b-109">Il [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callback informano il debugger quando una classe è stato aggiunta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="00d9b-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00d9b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00d9b-110">Requirements</span></span>  
 <span data-ttu-id="00d9b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00d9b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00d9b-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="00d9b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00d9b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00d9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00d9b-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00d9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
