---
title: Metodo ICorDebugManagedCallback::EvalComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1261942865419762fa454eb8d4bc5e5d99e86d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193174"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="d3378-102">Metodo ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="d3378-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="d3378-103">Notifica al debugger che è stata completata una valutazione.</span><span class="sxs-lookup"><span data-stu-id="d3378-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3378-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3378-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3378-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3378-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d3378-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata eseguita la valutazione.</span><span class="sxs-lookup"><span data-stu-id="d3378-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d3378-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata eseguita la valutazione.</span><span class="sxs-lookup"><span data-stu-id="d3378-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="d3378-108">[in] Un puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.</span><span class="sxs-lookup"><span data-stu-id="d3378-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3378-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3378-109">Requirements</span></span>  
 <span data-ttu-id="d3378-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3378-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3378-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3378-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3378-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3378-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3378-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d3378-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3378-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3378-114">See also</span></span>

- [<span data-ttu-id="d3378-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d3378-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
