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
ms.openlocfilehash: 1f1e42cd929d2d6282d282cf62dce00104b3a925
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210241"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="80fd7-102">Interfaccia ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="80fd7-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="80fd7-103">Rappresenta una stack frame di codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="80fd7-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="80fd7-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="80fd7-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80fd7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="80fd7-105">Methods</span></span>  
  
|<span data-ttu-id="80fd7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="80fd7-106">Method</span></span>|<span data-ttu-id="80fd7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80fd7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80fd7-108">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="80fd7-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="80fd7-109">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato.</span><span class="sxs-lookup"><span data-stu-id="80fd7-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="80fd7-110">Metodo EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="80fd7-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="80fd7-111">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="80fd7-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="80fd7-112">Metodo EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="80fd7-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="80fd7-113">Ottiene un enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="80fd7-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="80fd7-114">Metodo GetArgument</span><span class="sxs-lookup"><span data-stu-id="80fd7-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="80fd7-115">Ottiene il valore dell'argomento specificato in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="80fd7-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="80fd7-116">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="80fd7-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="80fd7-117">Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="80fd7-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="80fd7-118">Metodo GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="80fd7-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="80fd7-119">Ottiene il valore della variabile locale specificata in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="80fd7-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="80fd7-120">Metodo GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="80fd7-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="80fd7-121">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="80fd7-121">Not implemented.</span></span>|  
|[<span data-ttu-id="80fd7-122">Metodo GetStackValue</span><span class="sxs-lookup"><span data-stu-id="80fd7-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="80fd7-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="80fd7-123">Not implemented.</span></span>|  
|[<span data-ttu-id="80fd7-124">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="80fd7-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="80fd7-125">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="80fd7-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80fd7-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="80fd7-126">Remarks</span></span>  
 <span data-ttu-id="80fd7-127">L' `ICorDebugILFrame` interfaccia è un'interfaccia ICorDebugFrame specializzata.</span><span class="sxs-lookup"><span data-stu-id="80fd7-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="80fd7-128">Viene usato per i frame di codice MSIL o per i frame compilati JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="80fd7-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="80fd7-129">I frame compilati tramite JIT implementano l'interfaccia `ICorDebugILFrame` e l'interfaccia ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="80fd7-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80fd7-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="80fd7-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fd7-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80fd7-131">Requirements</span></span>  
 <span data-ttu-id="80fd7-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80fd7-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fd7-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80fd7-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80fd7-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80fd7-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80fd7-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fd7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fd7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80fd7-136">See also</span></span>

- [<span data-ttu-id="80fd7-137">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="80fd7-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
