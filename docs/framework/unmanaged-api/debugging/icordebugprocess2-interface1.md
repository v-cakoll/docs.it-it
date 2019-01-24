---
title: Interfaccia1 ICorDebugProcess2
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
ms.openlocfilehash: 0b37cb8ecd178b90a4dcd2d2eab9fa7c4cd3211d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647322"
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="47604-102">Interfaccia1 ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="47604-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="47604-103">Un'estensione logica dell'interfaccia ICorDebugProcess, che rappresenta un processo in esecuzione codice gestito.</span><span class="sxs-lookup"><span data-stu-id="47604-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47604-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="47604-104">Methods</span></span>  
  
|<span data-ttu-id="47604-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="47604-105">Method</span></span>|<span data-ttu-id="47604-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47604-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47604-107">Metodo ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47604-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="47604-108">Rimuove un punto di interruzione in corrispondenza dell'offset specificato che è stato impostato da una precedente chiamata a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="47604-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="47604-109">Metodo GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="47604-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="47604-110">Ottiene i flag che devono essere impostati per common language runtime (CLR) per caricare l'immagine nel processo di cui fa riferimento questo `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="47604-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="47604-111">Metodo GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="47604-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="47604-112">Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="47604-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="47604-113">Metodo GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="47604-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="47604-114">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="47604-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="47604-115">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="47604-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="47604-116">Ottiene la versione di CLR su cui è in esecuzione il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="47604-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="47604-117">Metodo SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="47604-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="47604-118">Imposta i flag necessari per il compilatore JIT just-in-time caricare un'immagine nel processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="47604-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="47604-119">Metodo SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47604-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="47604-120">Imposta un punto di interruzione non gestita in corrispondenza dell'offset di immagine nativa specificata.</span><span class="sxs-lookup"><span data-stu-id="47604-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47604-121">Note</span><span class="sxs-lookup"><span data-stu-id="47604-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47604-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="47604-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47604-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47604-123">Requirements</span></span>  
 <span data-ttu-id="47604-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47604-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47604-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47604-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47604-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47604-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47604-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47604-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47604-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47604-128">See also</span></span>
- [<span data-ttu-id="47604-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="47604-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
