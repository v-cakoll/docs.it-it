---
title: ICorDebugGenericValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="ae817-102">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="ae817-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="ae817-103">Sottoclasse di "ICorDebugValue" che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="ae817-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="ae817-104">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="ae817-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae817-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ae817-105">Methods</span></span>  
  
|<span data-ttu-id="ae817-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ae817-106">Method</span></span>|<span data-ttu-id="ae817-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae817-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae817-108">GetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="ae817-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="ae817-109">Il valore può essere copiato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="ae817-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="ae817-110">SetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="ae817-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="ae817-111">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="ae817-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae817-112">Note</span><span class="sxs-lookup"><span data-stu-id="ae817-112">Remarks</span></span>  
 <span data-ttu-id="ae817-113">`ICorDebugGenericValue`è un'interfaccia secondario perché non utilizzabili in remoto.</span><span class="sxs-lookup"><span data-stu-id="ae817-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="ae817-114">Per i tipi di riferimento, il valore è il riferimento piuttosto che il contenuto del riferimento.</span><span class="sxs-lookup"><span data-stu-id="ae817-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="ae817-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ae817-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae817-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ae817-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae817-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae817-117">Requirements</span></span>  
 <span data-ttu-id="ae817-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae817-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae817-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ae817-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae817-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae817-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae817-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae817-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae817-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae817-122">See Also</span></span>  
    
 [<span data-ttu-id="ae817-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ae817-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
