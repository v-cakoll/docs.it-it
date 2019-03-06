---
title: Metodo ICorDebugManagedCallback::EvalException
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e3ab185f1ca5571656ed9b4aa4352a007da4151
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484537"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="4a78a-102">Metodo ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="4a78a-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="4a78a-103">Notifica al debugger che una versione di valutazione è terminata con un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="4a78a-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a78a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a78a-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a78a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a78a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4a78a-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui la valutazione è terminata.</span><span class="sxs-lookup"><span data-stu-id="4a78a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4a78a-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è terminata la valutazione.</span><span class="sxs-lookup"><span data-stu-id="4a78a-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="4a78a-108">[in] Un puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.</span><span class="sxs-lookup"><span data-stu-id="4a78a-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a78a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a78a-109">Requirements</span></span>  
 <span data-ttu-id="4a78a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a78a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a78a-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a78a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a78a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a78a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a78a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a78a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a78a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a78a-114">See also</span></span>
- [<span data-ttu-id="4a78a-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4a78a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
