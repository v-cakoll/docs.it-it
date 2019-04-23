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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149071"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="c73bd-102">Interfaccia ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="c73bd-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="c73bd-103">Implementa i metodi ICorDebugEnum ed enumera le matrici ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="c73bd-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c73bd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c73bd-104">Methods</span></span>  
  
|<span data-ttu-id="c73bd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c73bd-105">Method</span></span>|<span data-ttu-id="c73bd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c73bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c73bd-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="c73bd-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="c73bd-108">Ottiene il numero specificato di `ICorDebugBreakpoint` istanze dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c73bd-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c73bd-109">Note</span><span class="sxs-lookup"><span data-stu-id="c73bd-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c73bd-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c73bd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c73bd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c73bd-111">Requirements</span></span>  
 <span data-ttu-id="c73bd-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c73bd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c73bd-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c73bd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c73bd-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c73bd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c73bd-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c73bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c73bd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c73bd-116">See also</span></span>

- [<span data-ttu-id="c73bd-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c73bd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
