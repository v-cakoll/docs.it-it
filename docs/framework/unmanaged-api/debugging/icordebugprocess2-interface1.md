---
title: ICorDebugProcess2 Interface1
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1588a37891d6a73c49cb1b9ccbc81d9dcdb7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420417"
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="6b23a-102">ICorDebugProcess2 Interface1</span><span class="sxs-lookup"><span data-stu-id="6b23a-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="6b23a-103">Estensione logica dell'interfaccia ICorDebugProcess, che rappresenta un processo in esecuzione codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6b23a-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b23a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6b23a-104">Methods</span></span>  
  
|<span data-ttu-id="6b23a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6b23a-105">Method</span></span>|<span data-ttu-id="6b23a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b23a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b23a-107">Metodo ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b23a-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="6b23a-108">Rimuove un punto di interruzione in corrispondenza dell'offset specificato che è stato impostato da una precedente chiamata a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="6b23a-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="6b23a-109">Metodo GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="6b23a-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="6b23a-110">Ottiene i flag che devono essere impostati per common language runtime (CLR) per caricare l'immagine nel processo a cui fa riferimento `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="6b23a-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="6b23a-111">Metodo GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="6b23a-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="6b23a-112">Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6b23a-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="6b23a-113">Metodo GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="6b23a-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="6b23a-114">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="6b23a-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="6b23a-115">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="6b23a-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="6b23a-116">Ottiene la versione di CLR in cui è in esecuzione il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="6b23a-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="6b23a-117">Metodo SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="6b23a-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="6b23a-118">Imposta i flag necessari per il compilatore di just-in-time (JIT) caricare un'immagine nel processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="6b23a-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="6b23a-119">Metodo SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b23a-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="6b23a-120">Imposta un punto di interruzione non gestita in corrispondenza dell'offset specificato immagini native.</span><span class="sxs-lookup"><span data-stu-id="6b23a-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b23a-121">Note</span><span class="sxs-lookup"><span data-stu-id="6b23a-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b23a-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6b23a-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b23a-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b23a-123">Requirements</span></span>  
 <span data-ttu-id="6b23a-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b23a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b23a-125">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6b23a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b23a-126">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6b23a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b23a-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b23a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b23a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b23a-128">See Also</span></span>  
 [<span data-ttu-id="6b23a-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6b23a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
