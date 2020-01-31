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
ms.openlocfilehash: cafa1c99a8988c199d866796911d1983aabb7208
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785058"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="f4d53-102">Metodo ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="f4d53-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="f4d53-103">Specifica l'oggetto gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="f4d53-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4d53-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4d53-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4d53-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="f4d53-106">in Puntatore a un oggetto [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) che rappresenta il gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="f4d53-106">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4d53-107">Note</span><span class="sxs-lookup"><span data-stu-id="f4d53-107">Remarks</span></span>  
 <span data-ttu-id="f4d53-108">L'oggetto gestore eventi per gli eventi non gestiti deve essere impostato dopo una chiamata a [ICorDebug:: Initialize](icordebug-initialize-method.md) e prima di qualsiasi chiamata a [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4d53-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="f4d53-109">Per gli scopi legacy, tuttavia, non è necessario impostare l'oggetto gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="f4d53-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="f4d53-110">In particolare, se `ICorDebug::CreateProcess` ha impostato il flag CREATE_SUSPENDED, non è possibile inviare gli eventi di debug nativi finché il thread principale non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="f4d53-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d53-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f4d53-111">Requirements</span></span>  
 <span data-ttu-id="f4d53-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4d53-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d53-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4d53-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4d53-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4d53-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4d53-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4d53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d53-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4d53-116">See also</span></span>

- [<span data-ttu-id="f4d53-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f4d53-117">ICorDebug Interface</span></span>](icordebug-interface.md)
