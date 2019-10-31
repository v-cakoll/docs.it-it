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
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134051"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="f92b1-102">Metodo ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="f92b1-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="f92b1-103">Specifica l'oggetto gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="f92b1-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f92b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f92b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f92b1-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="f92b1-106">in Puntatore a un oggetto [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) che rappresenta il gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="f92b1-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f92b1-107">Note</span><span class="sxs-lookup"><span data-stu-id="f92b1-107">Remarks</span></span>  
 <span data-ttu-id="f92b1-108">L'oggetto gestore eventi per gli eventi non gestiti deve essere impostato dopo una chiamata a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) e prima di qualsiasi chiamata a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="f92b1-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="f92b1-109">Per gli scopi legacy, tuttavia, non è necessario impostare l'oggetto gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo.</span><span class="sxs-lookup"><span data-stu-id="f92b1-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="f92b1-110">In particolare, se `ICorDebug::CreateProcess` ha impostato il flag CREATE_SUSPENDED, gli eventi di debug nativi non possono essere inviati fino a quando non viene ripreso il thread principale.</span><span class="sxs-lookup"><span data-stu-id="f92b1-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f92b1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f92b1-111">Requirements</span></span>  
 <span data-ttu-id="f92b1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f92b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f92b1-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f92b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f92b1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f92b1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f92b1-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f92b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92b1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f92b1-116">See also</span></span>

- [<span data-ttu-id="f92b1-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f92b1-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
