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
ms.openlocfilehash: 9e8aa71a79bee45d5a8e1f3448c781e6ba1ec605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414138"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="c9083-102">Metodo ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="c9083-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="c9083-103">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="c9083-103">This method has been deprecated.</span></span> <span data-ttu-id="c9083-104">Notifica al debugger che è stato inviato un evento relativo all'ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="c9083-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9083-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9083-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c9083-106">Note</span><span class="sxs-lookup"><span data-stu-id="c9083-106">Remarks</span></span>  
 <span data-ttu-id="c9083-107">Il `EditAndContinueRemap` metodo viene chiamato quando è stata tentata l'esecuzione del codice in una versione precedente di una funzione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="c9083-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="c9083-108">Common language runtime chiama il `EditAndContinueRemap` metodo per inviare un evento di modifica del mapping all'IDE.</span><span class="sxs-lookup"><span data-stu-id="c9083-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9083-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9083-109">Requirements</span></span>  
 <span data-ttu-id="c9083-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9083-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9083-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c9083-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9083-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c9083-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9083-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9083-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9083-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9083-114">See Also</span></span>  
 [<span data-ttu-id="c9083-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c9083-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
