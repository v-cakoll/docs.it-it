---
title: ICorDebugAppDomain Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain
helpviewer_keywords: ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19cf38920ed818dfbba9cd83bd64fdc408281e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="83819-102">ICorDebugAppDomain Interface1</span><span class="sxs-lookup"><span data-stu-id="83819-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="83819-103">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="83819-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="83819-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83819-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="83819-105">Methods</span></span>  
  
|<span data-ttu-id="83819-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="83819-106">Method</span></span>|<span data-ttu-id="83819-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83819-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83819-108">Attach (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="83819-109">Collega il debugger per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="83819-110">EnumerateAssemblies (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="83819-111">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="83819-112">EnumerateBreakpoints (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="83819-113">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="83819-114">EnumerateSteppers (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="83819-115">Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="83819-116">GetID (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="83819-117">Ottiene l'ID univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="83819-118">GetModuleFromMetaDataInterface (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="83819-119">Ottiene l'oggetto ICorDebugModule con l'interfaccia di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="83819-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="83819-120">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="83819-121">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="83819-122">GetObject (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="83819-123">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="83819-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="83819-124">GetProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="83819-125">Ottiene il processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="83819-126">IsAttached (metodo)</span><span class="sxs-lookup"><span data-stu-id="83819-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="83819-127">Determina se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="83819-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83819-128">Note</span><span class="sxs-lookup"><span data-stu-id="83819-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83819-129">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="83819-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83819-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83819-130">Requirements</span></span>  
 <span data-ttu-id="83819-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83819-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83819-132">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="83819-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83819-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83819-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83819-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83819-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83819-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83819-135">See Also</span></span>  
 [<span data-ttu-id="83819-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="83819-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
