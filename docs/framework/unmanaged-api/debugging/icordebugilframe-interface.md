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
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788573"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="c1198-102">Interfaccia ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="c1198-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="c1198-103">Rappresenta una stack frame di codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="c1198-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="c1198-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="c1198-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1198-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c1198-105">Methods</span></span>  
  
|<span data-ttu-id="c1198-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c1198-106">Method</span></span>|<span data-ttu-id="c1198-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1198-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1198-108">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="c1198-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="c1198-109">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato.</span><span class="sxs-lookup"><span data-stu-id="c1198-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="c1198-110">Metodo EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="c1198-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="c1198-111">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="c1198-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="c1198-112">Metodo EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="c1198-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="c1198-113">Ottiene un enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="c1198-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="c1198-114">Metodo GetArgument</span><span class="sxs-lookup"><span data-stu-id="c1198-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="c1198-115">Ottiene il valore dell'argomento specificato in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="c1198-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="c1198-116">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="c1198-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="c1198-117">Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c1198-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="c1198-118">Metodo GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="c1198-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="c1198-119">Ottiene il valore della variabile locale specificata in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="c1198-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="c1198-120">Metodo GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="c1198-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="c1198-121">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="c1198-121">Not implemented.</span></span>|  
|[<span data-ttu-id="c1198-122">Metodo GetStackValue</span><span class="sxs-lookup"><span data-stu-id="c1198-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="c1198-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="c1198-123">Not implemented.</span></span>|  
|[<span data-ttu-id="c1198-124">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="c1198-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="c1198-125">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="c1198-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1198-126">Note</span><span class="sxs-lookup"><span data-stu-id="c1198-126">Remarks</span></span>  
 <span data-ttu-id="c1198-127">L'interfaccia `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata.</span><span class="sxs-lookup"><span data-stu-id="c1198-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="c1198-128">Viene usato per i frame di codice MSIL o per i frame compilati JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="c1198-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="c1198-129">I frame compilati tramite JIT implementano sia l'interfaccia `ICorDebugILFrame` che l'interfaccia ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="c1198-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1198-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c1198-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1198-131">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c1198-131">Requirements</span></span>  
 <span data-ttu-id="c1198-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1198-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1198-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1198-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1198-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1198-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1198-135">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1198-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1198-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1198-136">See also</span></span>

- [<span data-ttu-id="c1198-137">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c1198-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
