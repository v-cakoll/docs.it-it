---
title: Interfaccia ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 04bdbc49217236bc6c05a718cb4d42067cafd8bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096666"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="a6e64-102">Interfaccia ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="a6e64-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="a6e64-103">Implementazione specializzata di ICorDebugFrame utilizzata per i frame nativi.</span><span class="sxs-lookup"><span data-stu-id="a6e64-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6e64-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a6e64-104">Methods</span></span>  
  
|<span data-ttu-id="a6e64-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a6e64-105">Method</span></span>|<span data-ttu-id="a6e64-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6e64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6e64-107">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="a6e64-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="a6e64-108">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="a6e64-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="a6e64-109">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="a6e64-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="a6e64-110">Ottiene l'offset del stack frame nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="a6e64-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="a6e64-111">Metodo GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="a6e64-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="a6e64-112">Ottiene un puntatore a un ICorDebugValue che rappresenta il valore di un argomento o di una variabile locale archiviata in due registri di memoria di un frame nativo.</span><span class="sxs-lookup"><span data-stu-id="a6e64-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="a6e64-113">Metodo GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="a6e64-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="a6e64-114">Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit bassi vengono archiviati nel registro specificato e i bit massimi vengono archiviati nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="a6e64-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="a6e64-115">Metodo GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="a6e64-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="a6e64-116">Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale archiviata nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="a6e64-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="a6e64-117">Metodo GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="a6e64-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="a6e64-118">Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit massimi vengono archiviati nel registro specificato e i bit bassi vengono archiviati nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="a6e64-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="a6e64-119">Metodo GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="a6e64-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="a6e64-120">Ottiene un puntatore a un `ICorDebugValue` che rappresenta il valore di un argomento o una variabile locale archiviata nel registro nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="a6e64-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="a6e64-121">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a6e64-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="a6e64-122">Ottiene un puntatore a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) che rappresenta il set di registri per questo `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="a6e64-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="a6e64-123">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="a6e64-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="a6e64-124">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="a6e64-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6e64-125">Note</span><span class="sxs-lookup"><span data-stu-id="a6e64-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6e64-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a6e64-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e64-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6e64-127">Requirements</span></span>  
 <span data-ttu-id="a6e64-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e64-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e64-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6e64-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6e64-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6e64-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6e64-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e64-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e64-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e64-132">See also</span></span>

- [<span data-ttu-id="a6e64-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a6e64-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
