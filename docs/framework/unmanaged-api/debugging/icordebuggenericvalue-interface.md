---
title: ICorDebugGenericValue Interface1
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
ms.openlocfilehash: 0081f020da673023e2c35f9599e9682215e2c9d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415064"
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="064a7-102">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="064a7-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="064a7-103">Sottoclasse di "ICorDebugValue" che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="064a7-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="064a7-104">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="064a7-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="064a7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="064a7-105">Methods</span></span>  
  
|<span data-ttu-id="064a7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="064a7-106">Method</span></span>|<span data-ttu-id="064a7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="064a7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="064a7-108">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="064a7-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="064a7-109">Il valore può essere copiato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="064a7-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="064a7-110">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="064a7-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="064a7-111">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="064a7-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="064a7-112">Note</span><span class="sxs-lookup"><span data-stu-id="064a7-112">Remarks</span></span>  
 <span data-ttu-id="064a7-113">`ICorDebugGenericValue` è un'interfaccia secondario perché è non utilizzabile in remoto.</span><span class="sxs-lookup"><span data-stu-id="064a7-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="064a7-114">Per i tipi di riferimento, il valore è il riferimento piuttosto che il contenuto del riferimento.</span><span class="sxs-lookup"><span data-stu-id="064a7-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="064a7-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="064a7-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="064a7-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="064a7-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="064a7-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="064a7-117">Requirements</span></span>  
 <span data-ttu-id="064a7-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="064a7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="064a7-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="064a7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="064a7-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="064a7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="064a7-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="064a7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064a7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="064a7-122">See Also</span></span>  
    
 [<span data-ttu-id="064a7-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="064a7-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
