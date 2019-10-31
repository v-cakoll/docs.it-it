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
ms.openlocfilehash: 01c247f838f66d1a77831755126a5a1f56870c1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095137"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="0fb46-102">Interfaccia ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="0fb46-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="0fb46-103">Rappresenta una stack frame di codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="0fb46-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="0fb46-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="0fb46-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0fb46-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0fb46-105">Methods</span></span>  
  
|<span data-ttu-id="0fb46-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="0fb46-106">Method</span></span>|<span data-ttu-id="0fb46-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fb46-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0fb46-108">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="0fb46-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="0fb46-109">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato.</span><span class="sxs-lookup"><span data-stu-id="0fb46-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="0fb46-110">Metodo EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="0fb46-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="0fb46-111">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="0fb46-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="0fb46-112">Metodo EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="0fb46-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="0fb46-113">Ottiene un enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="0fb46-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="0fb46-114">Metodo GetArgument</span><span class="sxs-lookup"><span data-stu-id="0fb46-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="0fb46-115">Ottiene il valore dell'argomento specificato in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="0fb46-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="0fb46-116">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="0fb46-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="0fb46-117">Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0fb46-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="0fb46-118">Metodo GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="0fb46-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="0fb46-119">Ottiene il valore della variabile locale specificata in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="0fb46-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="0fb46-120">Metodo GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="0fb46-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="0fb46-121">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0fb46-121">Not implemented.</span></span>|  
|[<span data-ttu-id="0fb46-122">Metodo GetStackValue</span><span class="sxs-lookup"><span data-stu-id="0fb46-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="0fb46-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0fb46-123">Not implemented.</span></span>|  
|[<span data-ttu-id="0fb46-124">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="0fb46-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="0fb46-125">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="0fb46-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fb46-126">Note</span><span class="sxs-lookup"><span data-stu-id="0fb46-126">Remarks</span></span>  
 <span data-ttu-id="0fb46-127">L'interfaccia `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata.</span><span class="sxs-lookup"><span data-stu-id="0fb46-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="0fb46-128">Viene usato per i frame di codice MSIL o per i frame compilati JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="0fb46-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="0fb46-129">I frame compilati tramite JIT implementano sia l'interfaccia `ICorDebugILFrame` che l'interfaccia ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="0fb46-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fb46-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0fb46-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb46-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fb46-131">Requirements</span></span>  
 <span data-ttu-id="0fb46-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fb46-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb46-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fb46-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb46-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fb46-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb46-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb46-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb46-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fb46-136">See also</span></span>

- [<span data-ttu-id="0fb46-137">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0fb46-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
