---
title: Interfaccia ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 5fb4a8a508cde4455bbee8c08432d3549e3fac43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122762"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="05899-102">Interfaccia ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="05899-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="05899-103">Implementa i metodi ICorDebugEnum ed enumera le matrici ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="05899-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05899-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="05899-104">Methods</span></span>  
  
|<span data-ttu-id="05899-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="05899-105">Method</span></span>|<span data-ttu-id="05899-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05899-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05899-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="05899-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="05899-108">Ottiene il numero specificato di istanze di `ICorDebugBreakpoint` dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="05899-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05899-109">Note</span><span class="sxs-lookup"><span data-stu-id="05899-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05899-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="05899-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05899-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05899-111">Requirements</span></span>  
 <span data-ttu-id="05899-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05899-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05899-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05899-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05899-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05899-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05899-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05899-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05899-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05899-116">See also</span></span>

- [<span data-ttu-id="05899-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="05899-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
