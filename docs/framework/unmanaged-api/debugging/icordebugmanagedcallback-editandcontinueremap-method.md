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
ms.openlocfilehash: 9cb956c0262fdcdb5971d049ea7b057aa4d952c0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781900"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="7e99b-102">Metodo ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="7e99b-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="7e99b-103">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="7e99b-103">This method has been deprecated.</span></span> <span data-ttu-id="7e99b-104">Notifica al debugger che è stato inviato un evento di modifica del mapping al Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="7e99b-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e99b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e99b-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7e99b-106">Note</span><span class="sxs-lookup"><span data-stu-id="7e99b-106">Remarks</span></span>  
 <span data-ttu-id="7e99b-107">Il metodo `EditAndContinueRemap` viene chiamato quando è stata tentata l'esecuzione del codice in una versione precedente di una funzione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="7e99b-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="7e99b-108">Il Common Language Runtime chiama il metodo `EditAndContinueRemap` per inviare un evento di modifica del mapping all'IDE.</span><span class="sxs-lookup"><span data-stu-id="7e99b-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e99b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7e99b-109">Requirements</span></span>  
 <span data-ttu-id="7e99b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e99b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e99b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e99b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e99b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e99b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e99b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e99b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e99b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e99b-114">See also</span></span>

- [<span data-ttu-id="7e99b-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7e99b-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
