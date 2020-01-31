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
ms.openlocfilehash: 3ae93081bd201f745fa47bc01a9c6fcbf6e9f63c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781865"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="7b495-102">Metodo ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="7b495-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="7b495-103">Notifica al debugger che una valutazione è stata terminata con un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="7b495-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b495-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b495-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b495-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b495-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7b495-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è terminata la valutazione.</span><span class="sxs-lookup"><span data-stu-id="7b495-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7b495-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui la valutazione è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="7b495-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="7b495-108">in Puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.</span><span class="sxs-lookup"><span data-stu-id="7b495-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b495-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7b495-109">Requirements</span></span>  
 <span data-ttu-id="7b495-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b495-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b495-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b495-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b495-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b495-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b495-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b495-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b495-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b495-114">See also</span></span>

- [<span data-ttu-id="7b495-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7b495-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
