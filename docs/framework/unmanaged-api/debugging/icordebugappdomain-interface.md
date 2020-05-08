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
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895179"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="350a0-102">Interfaccia ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="350a0-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="350a0-103">Fornisce metodi per il debug di domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="350a0-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="350a0-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="350a0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="350a0-105">Methods</span></span>  
  
|<span data-ttu-id="350a0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="350a0-106">Method</span></span>|<span data-ttu-id="350a0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="350a0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="350a0-108">Metodo Attach</span><span class="sxs-lookup"><span data-stu-id="350a0-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="350a0-109">Connette il debugger al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="350a0-110">Metodo EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="350a0-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="350a0-111">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="350a0-112">Metodo EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="350a0-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="350a0-113">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="350a0-114">Metodo EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="350a0-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="350a0-115">Ottiene un enumeratore per tutti i Stepper attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="350a0-116">Metodo GetId</span><span class="sxs-lookup"><span data-stu-id="350a0-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="350a0-117">Ottiene l'ID univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="350a0-118">Metodo GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="350a0-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="350a0-119">Ottiene l'oggetto ICorDebugModule con l'interfaccia dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="350a0-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="350a0-120">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="350a0-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="350a0-121">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="350a0-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="350a0-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="350a0-123">Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="350a0-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="350a0-124">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="350a0-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="350a0-125">Ottiene il processo che contiene il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="350a0-126">Metodo IsAttached</span><span class="sxs-lookup"><span data-stu-id="350a0-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="350a0-127">Determina se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="350a0-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="350a0-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="350a0-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="350a0-129">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="350a0-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="350a0-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="350a0-130">Requirements</span></span>  
 <span data-ttu-id="350a0-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="350a0-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="350a0-132">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="350a0-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="350a0-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="350a0-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="350a0-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="350a0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350a0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="350a0-135">See also</span></span>

- [<span data-ttu-id="350a0-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="350a0-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
