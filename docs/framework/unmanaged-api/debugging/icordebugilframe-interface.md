---
title: Interfaccia ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159802"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="8b5a2-102">Interfaccia ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="8b5a2-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="8b5a2-103">Rappresenta uno stack frame del codice Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="8b5a2-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="8b5a2-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b5a2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8b5a2-105">Methods</span></span>  
  
|<span data-ttu-id="8b5a2-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="8b5a2-106">Method</span></span>|<span data-ttu-id="8b5a2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b5a2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b5a2-108">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="8b5a2-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="8b5a2-109">Ottiene un valore che indica se è sicuro impostare il puntatore dell'istruzione nella posizione di offset specificata.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="8b5a2-110">Metodo EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="8b5a2-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="8b5a2-111">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="8b5a2-112">Metodo EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="8b5a2-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="8b5a2-113">Ottiene un enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="8b5a2-114">Metodo GetArgument</span><span class="sxs-lookup"><span data-stu-id="8b5a2-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="8b5a2-115">Ottiene il valore dell'argomento specificato in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="8b5a2-116">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="8b5a2-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="8b5a2-117">Ottiene il valore del puntatore dell'istruzione e un valore di combinazione bit per bit che descrive come è stato ottenuto il valore del puntatore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="8b5a2-118">Metodo GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="8b5a2-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="8b5a2-119">Ottiene il valore della variabile locale specificata in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="8b5a2-120">Metodo GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="8b5a2-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="8b5a2-121">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-121">Not implemented.</span></span>|  
|[<span data-ttu-id="8b5a2-122">Metodo GetStackValue</span><span class="sxs-lookup"><span data-stu-id="8b5a2-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="8b5a2-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-123">Not implemented.</span></span>|  
|[<span data-ttu-id="8b5a2-124">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="8b5a2-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="8b5a2-125">Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b5a2-126">Note</span><span class="sxs-lookup"><span data-stu-id="8b5a2-126">Remarks</span></span>  
 <span data-ttu-id="8b5a2-127">Il `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="8b5a2-128">Viene usato per i frame del codice MSIL o per just-in-time (JIT) i frame compilati.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="8b5a2-129">I frame con compilazione JIT implementano entrambi il `ICorDebugILFrame` interfaccia e l'interfaccia ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b5a2-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8b5a2-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b5a2-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b5a2-131">Requirements</span></span>  
 <span data-ttu-id="8b5a2-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b5a2-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b5a2-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b5a2-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b5a2-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b5a2-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b5a2-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b5a2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b5a2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b5a2-136">See also</span></span>

- [<span data-ttu-id="8b5a2-137">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8b5a2-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
