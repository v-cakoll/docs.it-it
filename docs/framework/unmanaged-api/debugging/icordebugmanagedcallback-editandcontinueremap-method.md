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
ms.openlocfilehash: 78b87b5c566b0d760a205757430123665fb2fcd3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213712"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="8a7e0-102">Metodo ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="8a7e0-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="8a7e0-103">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="8a7e0-103">This method has been deprecated.</span></span> <span data-ttu-id="8a7e0-104">Notifica al debugger che è stato inviato un evento di modifica del mapping al Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="8a7e0-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7e0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a7e0-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8a7e0-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8a7e0-106">Remarks</span></span>  
 <span data-ttu-id="8a7e0-107">Il `EditAndContinueRemap` metodo viene chiamato quando è stata tentata l'esecuzione del codice in una versione precedente di una funzione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="8a7e0-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="8a7e0-108">Il Common Language Runtime chiama il `EditAndContinueRemap` metodo per inviare un evento di modifica del mapping all'IDE.</span><span class="sxs-lookup"><span data-stu-id="8a7e0-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a7e0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a7e0-109">Requirements</span></span>  
 <span data-ttu-id="8a7e0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a7e0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a7e0-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a7e0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a7e0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a7e0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a7e0-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a7e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7e0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a7e0-114">See also</span></span>

- [<span data-ttu-id="8a7e0-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="8a7e0-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
