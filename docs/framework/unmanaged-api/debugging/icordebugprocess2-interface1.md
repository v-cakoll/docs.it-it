---
title: ICorDebugProcess2 Interface1
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
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80f6c35ba2ef2ec74293d0f025ddf20254f504a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="ec715-102">ICorDebugProcess2 Interface1</span><span class="sxs-lookup"><span data-stu-id="ec715-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="ec715-103">Estensione logica dell'interfaccia ICorDebugProcess, che rappresenta un processo in esecuzione codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ec715-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec715-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ec715-104">Methods</span></span>  
  
|<span data-ttu-id="ec715-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ec715-105">Method</span></span>|<span data-ttu-id="ec715-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec715-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec715-107">Metodo ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ec715-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="ec715-108">Rimuove un punto di interruzione in corrispondenza dell'offset specificato che è stato impostato da una precedente chiamata a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="ec715-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="ec715-109">Metodo GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="ec715-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="ec715-110">Ottiene i flag che devono essere impostati per common language runtime (CLR) per caricare l'immagine nel processo a cui fa riferimento `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="ec715-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="ec715-111">Metodo GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="ec715-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="ec715-112">Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ec715-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="ec715-113">Metodo GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="ec715-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="ec715-114">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="ec715-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="ec715-115">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="ec715-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="ec715-116">Ottiene la versione di CLR in cui è in esecuzione il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="ec715-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="ec715-117">Metodo SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="ec715-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="ec715-118">Imposta i flag necessari per il compilatore di just-in-time (JIT) caricare un'immagine nel processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="ec715-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="ec715-119">Metodo SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ec715-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="ec715-120">Imposta un punto di interruzione non gestita in corrispondenza dell'offset specificato immagini native.</span><span class="sxs-lookup"><span data-stu-id="ec715-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec715-121">Note</span><span class="sxs-lookup"><span data-stu-id="ec715-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec715-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ec715-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec715-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec715-123">Requirements</span></span>  
 <span data-ttu-id="ec715-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec715-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec715-125">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ec715-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec715-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec715-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec715-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec715-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec715-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec715-128">See Also</span></span>  
 [<span data-ttu-id="ec715-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ec715-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
