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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793030"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="f4173-102">Metodo ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="f4173-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="f4173-103">Controlla se i callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="f4173-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4173-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4173-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4173-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4173-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="f4173-106">in Impostare questo valore su `true` per consentire al Common Language Runtime (CLR) di chiamare i metodi di `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` quando si verificano gli eventi associati.</span><span class="sxs-lookup"><span data-stu-id="f4173-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="f4173-107">Il valore predefinito è `false` per i moduli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="f4173-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="f4173-108">Il valore è sempre `true` per i moduli dinamici e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f4173-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4173-109">Note</span><span class="sxs-lookup"><span data-stu-id="f4173-109">Remarks</span></span>  
 <span data-ttu-id="f4173-110">I callback `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` sono sempre abilitati per i moduli dinamici e non possono essere disabilitati.</span><span class="sxs-lookup"><span data-stu-id="f4173-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4173-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f4173-111">Requirements</span></span>  
 <span data-ttu-id="f4173-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4173-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4173-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4173-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4173-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4173-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4173-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4173-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4173-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4173-116">See also</span></span>
