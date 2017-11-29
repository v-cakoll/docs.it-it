---
title: ICorDebugILFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame
helpviewer_keywords: ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8d370fa971f698eb694127c72ff96499b85143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe-interface1"></a><span data-ttu-id="4197a-102">ICorDebugILFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="4197a-102">ICorDebugILFrame Interface1</span></span>
<span data-ttu-id="4197a-103">Rappresenta uno stack frame del codice Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4197a-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="4197a-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="4197a-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4197a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4197a-105">Methods</span></span>  
  
|<span data-ttu-id="4197a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4197a-106">Method</span></span>|<span data-ttu-id="4197a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4197a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4197a-108">CanSetIP (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="4197a-109">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione alla posizione di offset specificata.</span><span class="sxs-lookup"><span data-stu-id="4197a-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="4197a-110">EnumerateArguments (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="4197a-111">Ottiene un enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="4197a-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="4197a-112">EnumerateLocalVariables (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="4197a-113">Ottiene un enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="4197a-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="4197a-114">GetArgument (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="4197a-115">Ottiene il valore dell'argomento specificato in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="4197a-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="4197a-116">GetIP (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="4197a-117">Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive la modalità in cui è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4197a-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="4197a-118">GetLocalVariable (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="4197a-119">Ottiene il valore della variabile locale specificata in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="4197a-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="4197a-120">GetStackDepth (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="4197a-121">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="4197a-121">Not implemented.</span></span>|  
|[<span data-ttu-id="4197a-122">GetStackValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="4197a-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="4197a-123">Not implemented.</span></span>|  
|[<span data-ttu-id="4197a-124">SetIP (metodo)</span><span class="sxs-lookup"><span data-stu-id="4197a-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="4197a-125">Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="4197a-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4197a-126">Note</span><span class="sxs-lookup"><span data-stu-id="4197a-126">Remarks</span></span>  
 <span data-ttu-id="4197a-127">Il `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata.</span><span class="sxs-lookup"><span data-stu-id="4197a-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="4197a-128">Viene utilizzato per il frame di codice MSIL o per just-in-time (JIT) i frame compilati.</span><span class="sxs-lookup"><span data-stu-id="4197a-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="4197a-129">I frame compilato tramite JIT implementano sia la `ICorDebugILFrame` interfaccia e l'interfaccia ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="4197a-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4197a-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4197a-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4197a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4197a-131">Requirements</span></span>  
 <span data-ttu-id="4197a-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4197a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4197a-133">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4197a-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4197a-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4197a-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4197a-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4197a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4197a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4197a-136">See Also</span></span>  
 [<span data-ttu-id="4197a-137">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4197a-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
