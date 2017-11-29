---
title: ICorDebugObjectValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue
helpviewer_keywords: ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: acbfbbb8f7374b1ab783371d318bd3bcf89963fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="8e83b-102">ICorDebugObjectValue Interface1</span><span class="sxs-lookup"><span data-stu-id="8e83b-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="8e83b-103">Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="8e83b-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e83b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8e83b-104">Methods</span></span>  
  
|<span data-ttu-id="8e83b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8e83b-105">Method</span></span>|<span data-ttu-id="8e83b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e83b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e83b-107">GetClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="8e83b-108">Ottiene un puntatore a interfaccia a common language runtime (CLR) <xref:System.Type> dell'oggetto da questo `ICorDebugObjectValue` riferimenti.</span><span class="sxs-lookup"><span data-stu-id="8e83b-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="8e83b-109">GetContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="8e83b-110">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8e83b-110">Not implemented.</span></span>|  
|[<span data-ttu-id="8e83b-111">GetFieldValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="8e83b-112">Ottiene un puntatore a interfaccia a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="8e83b-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="8e83b-113">GetManagedCopy (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="8e83b-114">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="8e83b-114">Obsolete.</span></span> <span data-ttu-id="8e83b-115">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8e83b-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="8e83b-116">GetVirtualMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="8e83b-117">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8e83b-117">Not implemented.</span></span>|  
|[<span data-ttu-id="8e83b-118">IsValueClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="8e83b-119">Ottiene un valore che indica se l'oggetto a cui fa riferimento questo `ICorDebugObjectValue` è un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="8e83b-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="8e83b-120">SetFromManagedCopy (metodo)</span><span class="sxs-lookup"><span data-stu-id="8e83b-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="8e83b-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="8e83b-121">Obsolete.</span></span> <span data-ttu-id="8e83b-122">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8e83b-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e83b-123">Note</span><span class="sxs-lookup"><span data-stu-id="8e83b-123">Remarks</span></span>  
 <span data-ttu-id="8e83b-124">Un `ICorDebugObjectValue` rimane valido fino a quando non si continua il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="8e83b-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e83b-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8e83b-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e83b-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e83b-126">Requirements</span></span>  
 <span data-ttu-id="8e83b-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e83b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e83b-128">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8e83b-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e83b-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e83b-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e83b-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e83b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e83b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e83b-131">See Also</span></span>  
 [<span data-ttu-id="8e83b-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8e83b-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
