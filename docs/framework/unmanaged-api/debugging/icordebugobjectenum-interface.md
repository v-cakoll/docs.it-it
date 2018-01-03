---
title: ICorDebugObjectEnum Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum
helpviewer_keywords: ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f2610600d102177c80821c78e7d07f8aed1b6de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="2d9fe-102">ICorDebugObjectEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="2d9fe-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="2d9fe-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti dai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="2d9fe-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d9fe-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2d9fe-104">Methods</span></span>  
  
|<span data-ttu-id="2d9fe-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2d9fe-105">Method</span></span>|<span data-ttu-id="2d9fe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d9fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d9fe-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="2d9fe-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="2d9fe-108">Ottiene gli indirizzi virtuali relativi del numero specificato di oggetti nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="2d9fe-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d9fe-109">Note</span><span class="sxs-lookup"><span data-stu-id="2d9fe-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d9fe-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="2d9fe-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d9fe-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d9fe-111">Requirements</span></span>  
 <span data-ttu-id="2d9fe-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d9fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d9fe-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2d9fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d9fe-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d9fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d9fe-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d9fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9fe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d9fe-116">See Also</span></span>  
 [<span data-ttu-id="2d9fe-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2d9fe-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
