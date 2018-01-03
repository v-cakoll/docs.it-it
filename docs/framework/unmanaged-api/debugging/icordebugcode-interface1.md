---
title: ICorDebugCode Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86659b624ef01922b6c5d1db9b3ae3697d0128b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode-interface1"></a><span data-ttu-id="36986-102">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="36986-102">ICorDebugCode Interface1</span></span>
<span data-ttu-id="36986-103">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="36986-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36986-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="36986-104">Methods</span></span>  
  
|<span data-ttu-id="36986-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="36986-105">Method</span></span>|<span data-ttu-id="36986-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36986-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36986-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="36986-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="36986-108">Crea un punto di interruzione in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="36986-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="36986-109">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="36986-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="36986-110">Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="36986-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="36986-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="36986-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="36986-112">Ottiene il codice per la funzione specificata, formattata per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="36986-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="36986-113">Questo metodo è deprecato. Utilizzare [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="36986-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="36986-114">Metodo GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="36986-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="36986-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="36986-115">Not implemented.</span></span>|  
|[<span data-ttu-id="36986-116">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="36986-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="36986-117">Ottiene il "ICorDebugFunction" associato a questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="36986-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="36986-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="36986-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="36986-119">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping dagli offset MSIL agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="36986-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="36986-120">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="36986-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="36986-121">Ottiene le dimensioni, in byte, del codice binario rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="36986-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="36986-122">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="36986-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="36986-123">Ottiene il numero in base 1 che identifica la versione del codice da questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="36986-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="36986-124">Metodo IsIL</span><span class="sxs-lookup"><span data-stu-id="36986-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="36986-125">Ottiene un valore che indica se questo `ICorDebugCode` viene compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="36986-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36986-126">Note</span><span class="sxs-lookup"><span data-stu-id="36986-126">Remarks</span></span>  
 <span data-ttu-id="36986-127">`ICorDebugCode`può rappresentare MSIL o codice nativo.</span><span class="sxs-lookup"><span data-stu-id="36986-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="36986-128">Un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può avere zero o uno `ICorDebugCode` oggetti associati.</span><span class="sxs-lookup"><span data-stu-id="36986-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="36986-129">Un oggetto "ICorDebugFunction" che rappresenta il codice nativo può avere un numero qualsiasi di `ICorDebugCode` oggetti associati.</span><span class="sxs-lookup"><span data-stu-id="36986-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36986-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="36986-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36986-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36986-131">Requirements</span></span>  
 <span data-ttu-id="36986-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36986-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36986-133">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="36986-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36986-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36986-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36986-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36986-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36986-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36986-136">See Also</span></span>  
    
 [<span data-ttu-id="36986-137">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="36986-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="36986-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="36986-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
