---
title: Metodo ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be18d374bad07b590096acac985812c2e2ed9b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407584"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="0e6f5-102">Metodo ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="0e6f5-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="0e6f5-103">Specifica l'oggetto di gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e6f5-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e6f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e6f5-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e6f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e6f5-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="0e6f5-106">[in] Un puntatore a un [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) oggetto che rappresenta il gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e6f5-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e6f5-107">Note</span><span class="sxs-lookup"><span data-stu-id="0e6f5-107">Remarks</span></span>  
 <span data-ttu-id="0e6f5-108">Il gestore dell'evento oggetto non gestito eventi devono essere impostati dopo una chiamata a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) e prima delle chiamate a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug:: DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e6f5-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="0e6f5-109">Per applicazioni legacy, non è tuttavia necessario impostare l'oggetto di gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="0e6f5-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="0e6f5-110">In particolare, se `ICorDebug::CreateProcess` ha impostato il flag CREATE_SUSPENDED, gli eventi non possono essere inviati fino a quando non viene ripreso il thread principale di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="0e6f5-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e6f5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e6f5-111">Requirements</span></span>  
 <span data-ttu-id="0e6f5-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e6f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e6f5-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0e6f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e6f5-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0e6f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e6f5-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e6f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6f5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e6f5-116">See Also</span></span>  
 [<span data-ttu-id="0e6f5-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0e6f5-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
