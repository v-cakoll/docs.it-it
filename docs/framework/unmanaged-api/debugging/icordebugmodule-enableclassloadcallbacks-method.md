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
ms.openlocfilehash: 1ca3adf30ad633fcfb10a4b43a435698d2899597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213530"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="b2729-102">Metodo ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="b2729-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="b2729-103">Controlla se i callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="b2729-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2729-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2729-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2729-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2729-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="b2729-106">in Impostare questo valore su `true` per abilitare la Common Language Runtime (CLR) per chiamare i `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` metodi e quando si verificano gli eventi associati.</span><span class="sxs-lookup"><span data-stu-id="b2729-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="b2729-107">Il valore predefinito è `false` per i moduli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="b2729-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="b2729-108">Il valore è sempre `true` per i moduli dinamici e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="b2729-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2729-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2729-109">Remarks</span></span>  
 <span data-ttu-id="b2729-110">I `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` callback e sono sempre abilitati per i moduli dinamici e non possono essere disabilitati.</span><span class="sxs-lookup"><span data-stu-id="b2729-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2729-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2729-111">Requirements</span></span>  
 <span data-ttu-id="b2729-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2729-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2729-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2729-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2729-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2729-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2729-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2729-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2729-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2729-116">See also</span></span>
