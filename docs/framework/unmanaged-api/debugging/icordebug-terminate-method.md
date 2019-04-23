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
ms.openlocfilehash: 321298ce942b35d11a861c87cdf6b8714179ea97
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080839"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="c7ae7-102">Metodo ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="c7ae7-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="c7ae7-103">Termina il `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c7ae7-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7ae7-104">`Terminate` non deve essere chiamata fino a un [ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback è stato ricevuto per tutti i processi sottoposti a debug.</span><span class="sxs-lookup"><span data-stu-id="c7ae7-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ae7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7ae7-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c7ae7-106">Note</span><span class="sxs-lookup"><span data-stu-id="c7ae7-106">Remarks</span></span>  
 <span data-ttu-id="c7ae7-107">`Terminate` deve essere chiamato quando il `ICorDebug` oggetto non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="c7ae7-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ae7-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7ae7-108">Requirements</span></span>  
 <span data-ttu-id="c7ae7-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ae7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ae7-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7ae7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7ae7-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ae7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ae7-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ae7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ae7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ae7-113">See also</span></span>

- [<span data-ttu-id="c7ae7-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c7ae7-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
