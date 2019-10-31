---
title: Interfaccia ICorDebugObjectValue
ms.date: 03/30/2017
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
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129758"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="8296c-102">Interfaccia ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="8296c-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="8296c-103">Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="8296c-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8296c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8296c-104">Methods</span></span>  
  
|<span data-ttu-id="8296c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8296c-105">Method</span></span>|<span data-ttu-id="8296c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8296c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8296c-107">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="8296c-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="8296c-108">Ottiene un puntatore a interfaccia per la <xref:System.Type> di Common Language Runtime (CLR) dell'oggetto a cui fa riferimento questo `ICorDebugObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="8296c-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="8296c-109">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="8296c-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="8296c-110">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8296c-110">Not implemented.</span></span>|  
|[<span data-ttu-id="8296c-111">Metodo GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="8296c-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="8296c-112">Ottiene un puntatore a interfaccia a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="8296c-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="8296c-113">Metodo GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="8296c-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="8296c-114">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="8296c-114">Obsolete.</span></span> <span data-ttu-id="8296c-115">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8296c-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="8296c-116">Metodo GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="8296c-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="8296c-117">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8296c-117">Not implemented.</span></span>|  
|[<span data-ttu-id="8296c-118">Metodo IsValueClass</span><span class="sxs-lookup"><span data-stu-id="8296c-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="8296c-119">Ottiene un valore che indica se l'oggetto a cui fa riferimento questo `ICorDebugObjectValue` è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="8296c-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="8296c-120">Metodo SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="8296c-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="8296c-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="8296c-121">Obsolete.</span></span> <span data-ttu-id="8296c-122">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8296c-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8296c-123">Note</span><span class="sxs-lookup"><span data-stu-id="8296c-123">Remarks</span></span>  
 <span data-ttu-id="8296c-124">Un `ICorDebugObjectValue` rimane valido finché il processo di cui è in corso il debug non viene continuato.</span><span class="sxs-lookup"><span data-stu-id="8296c-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8296c-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8296c-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8296c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8296c-126">Requirements</span></span>  
 <span data-ttu-id="8296c-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8296c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8296c-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8296c-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8296c-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8296c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8296c-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8296c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8296c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8296c-131">See also</span></span>

- [<span data-ttu-id="8296c-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8296c-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
