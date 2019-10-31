---
title: Metodo ICorDebugManagedCallback::EditAndContinueRemap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 3fd1686eb268b9d4e347fe28e067a5321327dbd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137380"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="87875-102">Metodo ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="87875-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="87875-103">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="87875-103">This method has been deprecated.</span></span> <span data-ttu-id="87875-104">Notifica al debugger che è stato inviato un evento di modifica del mapping al Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="87875-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87875-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87875-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="87875-106">Note</span><span class="sxs-lookup"><span data-stu-id="87875-106">Remarks</span></span>  
 <span data-ttu-id="87875-107">Il metodo `EditAndContinueRemap` viene chiamato quando è stata tentata l'esecuzione del codice in una versione precedente di una funzione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="87875-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="87875-108">Il Common Language Runtime chiama il metodo `EditAndContinueRemap` per inviare un evento di modifica del mapping all'IDE.</span><span class="sxs-lookup"><span data-stu-id="87875-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87875-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87875-109">Requirements</span></span>  
 <span data-ttu-id="87875-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87875-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87875-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87875-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87875-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87875-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87875-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87875-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87875-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87875-114">See also</span></span>

- [<span data-ttu-id="87875-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="87875-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
