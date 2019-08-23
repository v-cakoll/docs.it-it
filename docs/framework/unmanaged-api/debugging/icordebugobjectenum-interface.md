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
ms.openlocfilehash: 1faa78150659b4397cd4174583b607e1f7841b8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943356"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="078d0-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="078d0-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="078d0-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="078d0-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="078d0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="078d0-104">Methods</span></span>  
  
|<span data-ttu-id="078d0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="078d0-105">Method</span></span>|<span data-ttu-id="078d0-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="078d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="078d0-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="078d0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="078d0-108">Ottiene l'RVA del numero specificato di oggetti dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="078d0-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="078d0-109">Note</span><span class="sxs-lookup"><span data-stu-id="078d0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="078d0-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="078d0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="078d0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="078d0-111">Requirements</span></span>  
 <span data-ttu-id="078d0-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="078d0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="078d0-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="078d0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="078d0-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="078d0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="078d0-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="078d0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078d0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="078d0-116">See also</span></span>

- [<span data-ttu-id="078d0-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="078d0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
