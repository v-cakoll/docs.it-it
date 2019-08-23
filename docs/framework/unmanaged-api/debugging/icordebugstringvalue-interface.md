---
title: Interfaccia ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cfaf886d09d843f4dbf61af55a9388454b050ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957420"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="bb55f-102">Interfaccia ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="bb55f-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="bb55f-103">Sottoclasse di ICorDebugHeapValue che si applica ai valori di stringa.</span><span class="sxs-lookup"><span data-stu-id="bb55f-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb55f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb55f-104">Methods</span></span>  
  
|<span data-ttu-id="bb55f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb55f-105">Method</span></span>|<span data-ttu-id="bb55f-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="bb55f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb55f-107">Metodo GetLength</span><span class="sxs-lookup"><span data-stu-id="bb55f-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="bb55f-108">Ottiene il numero di caratteri nella stringa a cui fa riferimento questo `ICorDebugStringValue`oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb55f-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="bb55f-109">Metodo GetString</span><span class="sxs-lookup"><span data-stu-id="bb55f-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="bb55f-110">Ottiene la stringa a cui fa riferimento `ICorDebugStringValue`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb55f-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb55f-111">Note</span><span class="sxs-lookup"><span data-stu-id="bb55f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb55f-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="bb55f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb55f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb55f-113">Requirements</span></span>  
 <span data-ttu-id="bb55f-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb55f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb55f-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bb55f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb55f-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb55f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb55f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb55f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb55f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb55f-118">See also</span></span>

- [<span data-ttu-id="bb55f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb55f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
