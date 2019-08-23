---
title: Metodo ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963134"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="5754d-102">Metodo ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="5754d-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="5754d-103">Termina l' `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5754d-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5754d-104">`Terminate`non deve essere chiamato fino a quando non viene ricevuto un callback [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) per tutti i processi di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="5754d-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5754d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5754d-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5754d-106">Note</span><span class="sxs-lookup"><span data-stu-id="5754d-106">Remarks</span></span>  
 <span data-ttu-id="5754d-107">`Terminate`deve essere chiamato quando l' `ICorDebug` oggetto non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="5754d-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5754d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5754d-108">Requirements</span></span>  
 <span data-ttu-id="5754d-109">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5754d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5754d-110">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5754d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5754d-111">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5754d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5754d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5754d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5754d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5754d-113">See also</span></span>

- [<span data-ttu-id="5754d-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5754d-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
