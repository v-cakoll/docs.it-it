---
title: Interfaccia ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12753ab65f9339e8f6c3049bb72755e87464eb1a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963102"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="54362-102">Interfaccia ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="54362-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="54362-103">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="54362-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="54362-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54362-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="54362-105">Methods</span></span>  
  
|<span data-ttu-id="54362-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="54362-106">Method</span></span>|<span data-ttu-id="54362-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="54362-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54362-108">Metodo Attach</span><span class="sxs-lookup"><span data-stu-id="54362-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="54362-109">Connette il debugger al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="54362-110">Metodo EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="54362-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="54362-111">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="54362-112">Metodo EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="54362-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="54362-113">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="54362-114">Metodo EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="54362-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="54362-115">Ottiene un enumeratore per tutti i Stepper attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="54362-116">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="54362-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="54362-117">Ottiene l'ID univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="54362-118">Metodo GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="54362-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="54362-119">Ottiene l'oggetto ICorDebugModule con l'interfaccia dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="54362-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="54362-120">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="54362-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="54362-121">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="54362-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="54362-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="54362-123">Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="54362-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="54362-124">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="54362-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="54362-125">Ottiene il processo che contiene il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="54362-126">Metodo IsAttached</span><span class="sxs-lookup"><span data-stu-id="54362-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="54362-127">Determina se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="54362-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54362-128">Note</span><span class="sxs-lookup"><span data-stu-id="54362-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54362-129">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="54362-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54362-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54362-130">Requirements</span></span>  
 <span data-ttu-id="54362-131">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54362-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54362-132">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="54362-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54362-133">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54362-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54362-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54362-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54362-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54362-135">See also</span></span>

- [<span data-ttu-id="54362-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="54362-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
