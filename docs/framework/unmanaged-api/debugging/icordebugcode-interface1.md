---
title: Interfaccia ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 8cb95fad4394e2ce9b7f922e720071d8c4434edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125584"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="34470-102">Interfaccia ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="34470-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="34470-103">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="34470-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34470-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="34470-104">Methods</span></span>  
  
|<span data-ttu-id="34470-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="34470-105">Method</span></span>|<span data-ttu-id="34470-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34470-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34470-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="34470-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="34470-108">Crea un punto di interruzione in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="34470-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="34470-109">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="34470-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="34470-110">Ottiene l'indirizzo RVA (relativo Virtual Address) del segmento di codice rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="34470-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="34470-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="34470-112">Ottiene tutto il codice per la funzione specificata, formattato per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="34470-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="34470-113">Questo metodo è stato deprecato. usare invece [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="34470-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="34470-114">Metodo GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="34470-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="34470-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="34470-115">Not implemented.</span></span>|  
|[<span data-ttu-id="34470-116">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="34470-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="34470-117">Ottiene l'oggetto "ICorDebugFunction" associato a questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="34470-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="34470-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="34470-119">Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL a offset nativi.</span><span class="sxs-lookup"><span data-stu-id="34470-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="34470-120">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="34470-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="34470-121">Ottiene la dimensione, in byte, del codice binario rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="34470-122">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="34470-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="34470-123">Ottiene il numero in base 1 che identifica la versione del codice rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="34470-124">Metodo IsIL</span><span class="sxs-lookup"><span data-stu-id="34470-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="34470-125">Ottiene un valore che indica se la `ICorDebugCode` è compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="34470-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34470-126">Note</span><span class="sxs-lookup"><span data-stu-id="34470-126">Remarks</span></span>  
 <span data-ttu-id="34470-127">`ICorDebugCode` possibile rappresentare codice MSIL o nativo.</span><span class="sxs-lookup"><span data-stu-id="34470-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="34470-128">A un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può essere associato uno o più oggetti `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="34470-129">A un oggetto "ICorDebugFunction" che rappresenta il codice nativo può essere associato un numero qualsiasi di oggetti `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="34470-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34470-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="34470-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34470-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34470-131">Requirements</span></span>  
 <span data-ttu-id="34470-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34470-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34470-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34470-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34470-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34470-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34470-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34470-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34470-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34470-136">See also</span></span>

- [<span data-ttu-id="34470-137">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="34470-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="34470-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="34470-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
