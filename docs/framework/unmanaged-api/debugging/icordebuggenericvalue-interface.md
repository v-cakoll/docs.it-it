---
title: Interfaccia ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36c2ed5529151a7ea18ccaffc2202ad6c69bcbd9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910223"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="6af08-102">Interfaccia ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="6af08-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="6af08-103">Sottoclasse di "ICorDebugValue" che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="6af08-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="6af08-104">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="6af08-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6af08-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6af08-105">Methods</span></span>  
  
|<span data-ttu-id="6af08-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="6af08-106">Method</span></span>|<span data-ttu-id="6af08-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6af08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6af08-108">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="6af08-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="6af08-109">Copia il valore nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="6af08-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="6af08-110">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="6af08-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="6af08-111">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="6af08-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6af08-112">Note</span><span class="sxs-lookup"><span data-stu-id="6af08-112">Remarks</span></span>  
 <span data-ttu-id="6af08-113">`ICorDebugGenericValue`è un'interfaccia secondaria perché non utilizzabile in remoto.</span><span class="sxs-lookup"><span data-stu-id="6af08-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="6af08-114">Per i tipi di riferimento, il valore è il riferimento anziché il contenuto del riferimento.</span><span class="sxs-lookup"><span data-stu-id="6af08-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="6af08-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6af08-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6af08-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6af08-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6af08-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6af08-117">Requirements</span></span>  
 <span data-ttu-id="6af08-118">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6af08-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6af08-119">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6af08-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6af08-120">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6af08-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6af08-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6af08-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af08-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6af08-122">See also</span></span>

- [<span data-ttu-id="6af08-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6af08-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
