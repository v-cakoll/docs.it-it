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
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791458"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="da8fc-102">Metodo ICorDebugThread2::InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="da8fc-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="da8fc-103">Consente a un debugger di intercettare l'eccezione corrente sul thread.</span><span class="sxs-lookup"><span data-stu-id="da8fc-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da8fc-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da8fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da8fc-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="da8fc-106">in Puntatore a un ICorDebugFrame che rappresenta il stack frame attivo.</span><span class="sxs-lookup"><span data-stu-id="da8fc-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da8fc-107">Note</span><span class="sxs-lookup"><span data-stu-id="da8fc-107">Remarks</span></span>  
 <span data-ttu-id="da8fc-108">Il metodo `InterceptCurrentException` può essere chiamato tra un callback di eccezione ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) o [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) e la chiamata associata a [ICorDebugController:: continue](icordebugcontroller-continue-method.md).</span><span class="sxs-lookup"><span data-stu-id="da8fc-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da8fc-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="da8fc-109">Requirements</span></span>  
 <span data-ttu-id="da8fc-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da8fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8fc-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da8fc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da8fc-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da8fc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da8fc-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da8fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
