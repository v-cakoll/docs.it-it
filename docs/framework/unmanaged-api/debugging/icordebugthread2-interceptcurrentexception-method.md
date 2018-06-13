---
title: Metodo ICorDebugThread2::InterceptCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f417fcd001d9e442ae518dbcd9df26eecb6efae9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421974"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="87473-102">Metodo ICorDebugThread2::InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="87473-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="87473-103">Consente a un debugger intercettare l'eccezione corrente su questo thread.</span><span class="sxs-lookup"><span data-stu-id="87473-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87473-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87473-104">Syntax</span></span>  
  
```  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87473-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87473-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="87473-106">[in] Un puntatore a un'interfaccia ICorDebugFrame che rappresenta lo stack frame attivo.</span><span class="sxs-lookup"><span data-stu-id="87473-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87473-107">Note</span><span class="sxs-lookup"><span data-stu-id="87473-107">Remarks</span></span>  
 <span data-ttu-id="87473-108">Il `InterceptCurrentException` metodo può essere chiamato tra un callback di eccezione ([ICorDebugManagedCallback:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) o [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) e la chiamata a associata[ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span><span class="sxs-lookup"><span data-stu-id="87473-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87473-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87473-109">Requirements</span></span>  
 <span data-ttu-id="87473-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87473-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87473-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="87473-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87473-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="87473-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87473-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87473-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
