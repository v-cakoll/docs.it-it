---
title: Interfaccia ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452216a2ba4e8013d107977d82eae1508b2aba78
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967763"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="1d913-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="1d913-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="1d913-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti dai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="1d913-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d913-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1d913-104">Methods</span></span>  
  
|<span data-ttu-id="1d913-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1d913-105">Method</span></span>|<span data-ttu-id="1d913-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d913-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d913-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="1d913-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="1d913-108">Ottiene il RVA del numero specificato di oggetti dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="1d913-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d913-109">Note</span><span class="sxs-lookup"><span data-stu-id="1d913-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d913-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1d913-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d913-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d913-111">Requirements</span></span>  
 <span data-ttu-id="1d913-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d913-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d913-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d913-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d913-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d913-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d913-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d913-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d913-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d913-116">See also</span></span>
- [<span data-ttu-id="1d913-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1d913-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
