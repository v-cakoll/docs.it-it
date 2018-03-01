---
title: Metodo ICorDebug::SetUnmanagedHandler
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c1b6da9db047321583de8c3c9238ed9ad4d4ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="d35aa-102">Metodo ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="d35aa-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="d35aa-103">Specifica l'oggetto di gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="d35aa-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d35aa-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d35aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d35aa-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d35aa-106">[in] Un puntatore a un [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) oggetto che rappresenta il gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="d35aa-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d35aa-107">Note</span><span class="sxs-lookup"><span data-stu-id="d35aa-107">Remarks</span></span>  
 <span data-ttu-id="d35aa-108">Il gestore dell'evento oggetto non gestito eventi devono essere impostati dopo una chiamata a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) e prima delle chiamate a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug:: DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="d35aa-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="d35aa-109">Per applicazioni legacy, non è tuttavia necessario impostare l'oggetto di gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="d35aa-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="d35aa-110">In particolare, se `ICorDebug::CreateProcess` ha impostato il flag CREATE_SUSPENDED, gli eventi non possono essere inviati fino a quando non viene ripreso il thread principale di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="d35aa-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d35aa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d35aa-111">Requirements</span></span>  
 <span data-ttu-id="d35aa-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d35aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d35aa-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d35aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d35aa-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d35aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d35aa-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d35aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35aa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d35aa-116">See Also</span></span>  
 [<span data-ttu-id="d35aa-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="d35aa-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
