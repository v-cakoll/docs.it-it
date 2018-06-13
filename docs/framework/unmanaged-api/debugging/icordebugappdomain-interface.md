---
title: ICorDebugAppDomain Interface1
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
ms.openlocfilehash: 84a11b6264ac0e241c1975eea5626edbdddce206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406877"
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="a2fb5-102">ICorDebugAppDomain Interface1</span><span class="sxs-lookup"><span data-stu-id="a2fb5-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="a2fb5-103">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="a2fb5-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2fb5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2fb5-105">Methods</span></span>  
  
|<span data-ttu-id="a2fb5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2fb5-106">Method</span></span>|<span data-ttu-id="a2fb5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2fb5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2fb5-108">Metodo Attach</span><span class="sxs-lookup"><span data-stu-id="a2fb5-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="a2fb5-109">Collega il debugger per il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-110">Metodo EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="a2fb5-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="a2fb5-111">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-112">Metodo EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="a2fb5-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="a2fb5-113">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-114">Metodo EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="a2fb5-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="a2fb5-115">Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-116">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="a2fb5-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="a2fb5-117">Ottiene l'ID univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-118">Metodo GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="a2fb5-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="a2fb5-119">Ottiene l'oggetto ICorDebugModule con l'interfaccia di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="a2fb5-120">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="a2fb5-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="a2fb5-121">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="a2fb5-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="a2fb5-123">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a2fb5-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-124">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="a2fb5-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="a2fb5-125">Ottiene il processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="a2fb5-126">Metodo IsAttached</span><span class="sxs-lookup"><span data-stu-id="a2fb5-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="a2fb5-127">Determina se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2fb5-128">Note</span><span class="sxs-lookup"><span data-stu-id="a2fb5-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2fb5-129">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a2fb5-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2fb5-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2fb5-130">Requirements</span></span>  
 <span data-ttu-id="a2fb5-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2fb5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2fb5-132">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a2fb5-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2fb5-133">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a2fb5-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2fb5-134">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2fb5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fb5-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2fb5-135">See Also</span></span>  
 [<span data-ttu-id="a2fb5-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2fb5-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
