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
ms.openlocfilehash: 70ae72968c3411a6732b09c0afe3d82931410cb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130811"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="1aacd-102">Metodo ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="1aacd-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="1aacd-103">Notifica al debugger che una valutazione è stata terminata con un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1aacd-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aacd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1aacd-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aacd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1aacd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1aacd-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è terminata la valutazione.</span><span class="sxs-lookup"><span data-stu-id="1aacd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1aacd-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui la valutazione è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="1aacd-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="1aacd-108">in Puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.</span><span class="sxs-lookup"><span data-stu-id="1aacd-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aacd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1aacd-109">Requirements</span></span>  
 <span data-ttu-id="1aacd-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aacd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aacd-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1aacd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1aacd-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aacd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aacd-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aacd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aacd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aacd-114">See also</span></span>

- [<span data-ttu-id="1aacd-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="1aacd-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
