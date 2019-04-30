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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1bdb14e8c3a61a2b94cef778660eeb5c85c34df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988241"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="6e398-102">Metodo ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="6e398-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="6e398-103">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="6e398-103">This method has been deprecated.</span></span> <span data-ttu-id="6e398-104">Notifica al debugger che è stato inviato un evento di modifica del mapping per l'ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="6e398-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e398-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e398-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e398-106">Note</span><span class="sxs-lookup"><span data-stu-id="6e398-106">Remarks</span></span>  
 <span data-ttu-id="6e398-107">Il `EditAndContinueRemap` metodo viene chiamato quando è stata tentata l'esecuzione del codice in una versione precedente di una funzione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6e398-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="6e398-108">Il common language runtime chiama il `EditAndContinueRemap` metodo per inviare un evento di modifica del mapping all'IDE.</span><span class="sxs-lookup"><span data-stu-id="6e398-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e398-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e398-109">Requirements</span></span>  
 <span data-ttu-id="6e398-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e398-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e398-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e398-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e398-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e398-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e398-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e398-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e398-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e398-114">See also</span></span>

- [<span data-ttu-id="6e398-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6e398-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
