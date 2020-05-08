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
ms.openlocfilehash: 7c3251b2cf7a4d0d97df0e6ecc9b332e3ed8e500
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895331"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="e5564-102">Metodo ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="e5564-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="e5564-103">Specifica l'oggetto gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="e5564-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5564-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5564-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5564-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5564-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="e5564-106">in Puntatore a un oggetto [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) che rappresenta il gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="e5564-106">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5564-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5564-107">Remarks</span></span>  
 <span data-ttu-id="e5564-108">L'oggetto gestore eventi per gli eventi non gestiti deve essere impostato dopo una chiamata a [ICorDebug:: Initialize](icordebug-initialize-method.md) e prima di qualsiasi chiamata a [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5564-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="e5564-109">Per gli scopi legacy, tuttavia, non è necessario impostare l'oggetto gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="e5564-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="e5564-110">In particolare, `ICorDebug::CreateProcess` se ha impostato il flag di CREATE_SUSPENDED, non è possibile inviare gli eventi di debug nativi finché il thread principale non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="e5564-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5564-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5564-111">Requirements</span></span>  
 <span data-ttu-id="e5564-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5564-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5564-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5564-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5564-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5564-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5564-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5564-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5564-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5564-116">See also</span></span>

- [<span data-ttu-id="e5564-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e5564-117">ICorDebug Interface</span></span>](icordebug-interface.md)
