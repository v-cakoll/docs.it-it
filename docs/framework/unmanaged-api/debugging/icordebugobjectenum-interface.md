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
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096146"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="b1cd6-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="b1cd6-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="b1cd6-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="b1cd6-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1cd6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b1cd6-104">Methods</span></span>  
  
|<span data-ttu-id="b1cd6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b1cd6-105">Method</span></span>|<span data-ttu-id="b1cd6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1cd6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1cd6-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="b1cd6-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="b1cd6-108">Ottiene l'RVA del numero specificato di oggetti dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="b1cd6-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1cd6-109">Note</span><span class="sxs-lookup"><span data-stu-id="b1cd6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1cd6-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b1cd6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1cd6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1cd6-111">Requirements</span></span>  
 <span data-ttu-id="b1cd6-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1cd6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1cd6-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1cd6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1cd6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1cd6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1cd6-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1cd6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1cd6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1cd6-116">See also</span></span>

- [<span data-ttu-id="b1cd6-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b1cd6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
