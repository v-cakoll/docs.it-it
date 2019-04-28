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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645304"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="3ca4f-102">Interfaccia ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="3ca4f-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="3ca4f-103">Implementa i metodi ICorDebugEnum ed enumera le matrici ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ca4f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3ca4f-104">Methods</span></span>  
  
|<span data-ttu-id="3ca4f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3ca4f-105">Method</span></span>|<span data-ttu-id="3ca4f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ca4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ca4f-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="3ca4f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="3ca4f-108">Ottiene il numero specificato di `ICorDebugBreakpoint` istanze dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca4f-109">Note</span><span class="sxs-lookup"><span data-stu-id="3ca4f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ca4f-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="3ca4f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca4f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ca4f-111">Requirements</span></span>  
 <span data-ttu-id="3ca4f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca4f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca4f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ca4f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ca4f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca4f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca4f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca4f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca4f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca4f-116">See also</span></span>

- [<span data-ttu-id="3ca4f-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3ca4f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
