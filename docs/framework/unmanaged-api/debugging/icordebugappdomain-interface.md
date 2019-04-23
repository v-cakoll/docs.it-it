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
ms.openlocfilehash: 40619aa40f9924d94c82541eb8d30790e774a675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141505"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="98f06-102">Interfaccia ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="98f06-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="98f06-103">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="98f06-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="98f06-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98f06-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="98f06-105">Methods</span></span>  
  
|<span data-ttu-id="98f06-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="98f06-106">Method</span></span>|<span data-ttu-id="98f06-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98f06-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98f06-108">Metodo Attach</span><span class="sxs-lookup"><span data-stu-id="98f06-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="98f06-109">Il debugger viene connesso al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="98f06-110">Metodo EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="98f06-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="98f06-111">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="98f06-112">Metodo EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="98f06-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="98f06-113">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="98f06-114">Metodo EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="98f06-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="98f06-115">Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="98f06-116">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="98f06-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="98f06-117">Ottiene l'ID univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="98f06-118">Metodo GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="98f06-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="98f06-119">Ottiene l'oggetto ICorDebugModule con l'interfaccia dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="98f06-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="98f06-120">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="98f06-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="98f06-121">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="98f06-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="98f06-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="98f06-123">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="98f06-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="98f06-124">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="98f06-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="98f06-125">Ottiene il processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="98f06-126">Metodo IsAttached</span><span class="sxs-lookup"><span data-stu-id="98f06-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="98f06-127">Determina se il debugger è collegato al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98f06-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98f06-128">Note</span><span class="sxs-lookup"><span data-stu-id="98f06-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98f06-129">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="98f06-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f06-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98f06-130">Requirements</span></span>  
 <span data-ttu-id="98f06-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98f06-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98f06-132">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98f06-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98f06-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98f06-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98f06-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98f06-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f06-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98f06-135">See also</span></span>

- [<span data-ttu-id="98f06-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="98f06-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
