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
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207486"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="ec6ac-102">Interfaccia ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="ec6ac-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="ec6ac-103">Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec6ac-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ec6ac-104">Methods</span></span>  
  
|<span data-ttu-id="ec6ac-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ec6ac-105">Method</span></span>|<span data-ttu-id="ec6ac-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec6ac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec6ac-107">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="ec6ac-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="ec6ac-108">Ottiene un puntatore a interfaccia per il Common Language Runtime (CLR) <xref:System.Type> dell'oggetto a cui `ICorDebugObjectValue` fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="ec6ac-109">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="ec6ac-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="ec6ac-110">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-110">Not implemented.</span></span>|  
|[<span data-ttu-id="ec6ac-111">Metodo GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="ec6ac-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="ec6ac-112">Ottiene un puntatore a interfaccia a un [ICorDebugValue](icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="ec6ac-113">Metodo GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="ec6ac-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="ec6ac-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-114">Obsolete.</span></span> <span data-ttu-id="ec6ac-115">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="ec6ac-116">Metodo GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="ec6ac-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="ec6ac-117">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-117">Not implemented.</span></span>|  
|[<span data-ttu-id="ec6ac-118">Metodo IsValueClass</span><span class="sxs-lookup"><span data-stu-id="ec6ac-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="ec6ac-119">Ottiene un valore che indica se l'oggetto a cui fa riferimento `ICorDebugObjectValue` è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="ec6ac-120">Metodo SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="ec6ac-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="ec6ac-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-121">Obsolete.</span></span> <span data-ttu-id="ec6ac-122">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6ac-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ec6ac-123">Remarks</span></span>  
 <span data-ttu-id="ec6ac-124">Un `ICorDebugObjectValue` rimane valido fino a quando il processo di cui è in corso il debug non viene continuato.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec6ac-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ec6ac-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec6ac-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec6ac-126">Requirements</span></span>  
 <span data-ttu-id="ec6ac-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec6ac-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec6ac-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec6ac-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec6ac-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec6ac-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec6ac-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec6ac-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6ac-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec6ac-131">See also</span></span>

- [<span data-ttu-id="ec6ac-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ec6ac-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
