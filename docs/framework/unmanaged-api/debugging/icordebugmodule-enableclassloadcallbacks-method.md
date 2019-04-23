---
title: Metodo ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a838748414f9d89cdc7ff469f7f5cc5e11b9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108303"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="b64bf-102">Metodo ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="b64bf-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="b64bf-103">Controlli se il [LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) i callback vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="b64bf-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b64bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b64bf-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b64bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b64bf-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="b64bf-106">[in] Impostare questo valore su `true` per abilitare common language runtime (CLR) per chiamare il `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` metodi quando si verificano gli eventi associati.</span><span class="sxs-lookup"><span data-stu-id="b64bf-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="b64bf-107">Il valore predefinito è `false` per i moduli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="b64bf-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="b64bf-108">Il valore è sempre `true` per i moduli dinamici e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="b64bf-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b64bf-109">Note</span><span class="sxs-lookup"><span data-stu-id="b64bf-109">Remarks</span></span>  
 <span data-ttu-id="b64bf-110">Il `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` callback sono sempre abilitati per i moduli dinamici e non può essere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b64bf-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b64bf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b64bf-111">Requirements</span></span>  
 <span data-ttu-id="b64bf-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b64bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b64bf-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b64bf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b64bf-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b64bf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b64bf-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b64bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64bf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b64bf-116">See also</span></span>
