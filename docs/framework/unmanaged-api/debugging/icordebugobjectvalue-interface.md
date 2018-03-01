---
title: ICorDebugObjectValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6dfde9f212936b1a0d0f5a6e76eafd4a2e62356c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="03716-102">ICorDebugObjectValue Interface1</span><span class="sxs-lookup"><span data-stu-id="03716-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="03716-103">Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="03716-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03716-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="03716-104">Methods</span></span>  
  
|<span data-ttu-id="03716-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="03716-105">Method</span></span>|<span data-ttu-id="03716-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03716-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03716-107">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="03716-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="03716-108">Ottiene un puntatore a interfaccia a common language runtime (CLR) <xref:System.Type> dell'oggetto da questo `ICorDebugObjectValue` riferimenti.</span><span class="sxs-lookup"><span data-stu-id="03716-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="03716-109">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="03716-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="03716-110">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="03716-110">Not implemented.</span></span>|  
|[<span data-ttu-id="03716-111">Metodo GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="03716-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="03716-112">Ottiene un puntatore a interfaccia a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="03716-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="03716-113">Metodo GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="03716-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="03716-114">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="03716-114">Obsolete.</span></span> <span data-ttu-id="03716-115">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="03716-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="03716-116">Metodo GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="03716-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="03716-117">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="03716-117">Not implemented.</span></span>|  
|[<span data-ttu-id="03716-118">Metodo IsValueClass</span><span class="sxs-lookup"><span data-stu-id="03716-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="03716-119">Ottiene un valore che indica se l'oggetto a cui fa riferimento questo `ICorDebugObjectValue` è un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="03716-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="03716-120">Metodo SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="03716-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="03716-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="03716-121">Obsolete.</span></span> <span data-ttu-id="03716-122">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="03716-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03716-123">Note</span><span class="sxs-lookup"><span data-stu-id="03716-123">Remarks</span></span>  
 <span data-ttu-id="03716-124">Un `ICorDebugObjectValue` rimane valido fino a quando non si continua il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="03716-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03716-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="03716-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03716-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03716-126">Requirements</span></span>  
 <span data-ttu-id="03716-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03716-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03716-128">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="03716-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03716-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03716-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03716-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03716-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03716-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03716-131">See Also</span></span>  
 [<span data-ttu-id="03716-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="03716-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
