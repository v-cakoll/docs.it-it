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
ms.openlocfilehash: ce4c1b73ab806958627bb68bfdcfcae890bc5e67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709832"
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="fd4f0-102">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="fd4f0-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="fd4f0-103">Sottoclasse di "ICorDebugValue" che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="fd4f0-104">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd4f0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fd4f0-105">Methods</span></span>  
  
|<span data-ttu-id="fd4f0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="fd4f0-106">Method</span></span>|<span data-ttu-id="fd4f0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd4f0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd4f0-108">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="fd4f0-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="fd4f0-109">Valore copiato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="fd4f0-110">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="fd4f0-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="fd4f0-111">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd4f0-112">Note</span><span class="sxs-lookup"><span data-stu-id="fd4f0-112">Remarks</span></span>  
 <span data-ttu-id="fd4f0-113">`ICorDebugGenericValue` è una sotto-interfaccia perché è non utilizzabili in remoto.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="fd4f0-114">Per i tipi riferimento, il valore è il riferimento anziché il contenuto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="fd4f0-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4f0-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fd4f0-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd4f0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd4f0-117">Requirements</span></span>  
 <span data-ttu-id="fd4f0-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4f0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4f0-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd4f0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd4f0-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd4f0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd4f0-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4f0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4f0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd4f0-122">See also</span></span>

- [<span data-ttu-id="fd4f0-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fd4f0-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
