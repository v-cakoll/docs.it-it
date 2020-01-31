---
title: Interfaccia ICorDebugProcess2
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
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792501"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="a2f97-102">Interfaccia ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="a2f97-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="a2f97-103">Estensione logica dell'interfaccia ICorDebugProcess, che rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a2f97-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2f97-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2f97-104">Methods</span></span>  
  
|<span data-ttu-id="a2f97-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2f97-105">Method</span></span>|<span data-ttu-id="a2f97-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2f97-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2f97-107">Metodo ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a2f97-107">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="a2f97-108">Rimuove un punto di interruzione in corrispondenza dell'offset specificato impostato da una chiamata precedente a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a2f97-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="a2f97-109">Metodo GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a2f97-109">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="a2f97-110">Ottiene i flag che devono essere impostati per il Common Language Runtime (CLR) per caricare l'immagine nel processo a cui fa riferimento questo `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="a2f97-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="a2f97-111">Metodo GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="a2f97-111">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="a2f97-112">Ottiene un puntatore di riferimento all'oggetto gestito specificato con un handle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2f97-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="a2f97-113">Metodo GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="a2f97-113">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="a2f97-114">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="a2f97-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="a2f97-115">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="a2f97-115">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="a2f97-116">Ottiene la versione di CLR su cui è in esecuzione il processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="a2f97-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="a2f97-117">Metodo SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a2f97-117">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="a2f97-118">Imposta i flag necessari per il compilatore JIT (just-in-Time) per caricare un'immagine nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="a2f97-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="a2f97-119">Metodo SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a2f97-119">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="a2f97-120">Imposta un punto di interruzione non gestito in corrispondenza dell'offset dell'immagine nativa specificato.</span><span class="sxs-lookup"><span data-stu-id="a2f97-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f97-121">Note</span><span class="sxs-lookup"><span data-stu-id="a2f97-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2f97-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a2f97-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f97-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a2f97-123">Requirements</span></span>  
 <span data-ttu-id="a2f97-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2f97-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f97-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2f97-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2f97-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2f97-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2f97-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f97-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f97-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2f97-128">See also</span></span>

- [<span data-ttu-id="a2f97-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2f97-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
