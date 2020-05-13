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
ms.openlocfilehash: dd87745a29514a2f9f05aa142baae4e05d4b4a7b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206607"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="191c9-102">Interfaccia ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="191c9-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="191c9-103">Implementazione specializzata di ICorDebugFrame utilizzata per i frame nativi.</span><span class="sxs-lookup"><span data-stu-id="191c9-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="191c9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="191c9-104">Methods</span></span>  
  
|<span data-ttu-id="191c9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="191c9-105">Method</span></span>|<span data-ttu-id="191c9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="191c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="191c9-107">Metodo CanSetIP</span><span class="sxs-lookup"><span data-stu-id="191c9-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="191c9-108">Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="191c9-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="191c9-109">Metodo GetIP</span><span class="sxs-lookup"><span data-stu-id="191c9-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="191c9-110">Ottiene l'offset del stack frame nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="191c9-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="191c9-111">Metodo GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="191c9-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="191c9-112">Ottiene un puntatore a un ICorDebugValue che rappresenta il valore di un argomento o di una variabile locale archiviata in due registri di memoria di un frame nativo.</span><span class="sxs-lookup"><span data-stu-id="191c9-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="191c9-113">Metodo GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="191c9-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="191c9-114">Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit bassi vengono archiviati nel registro specificato e i bit massimi vengono archiviati nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="191c9-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="191c9-115">Metodo GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="191c9-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="191c9-116">Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale archiviata nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="191c9-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="191c9-117">Metodo GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="191c9-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="191c9-118">Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit massimi vengono archiviati nel registro specificato e i bit bassi vengono archiviati nell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="191c9-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="191c9-119">Metodo GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="191c9-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="191c9-120">Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di un argomento o una variabile locale archiviata nel registro nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="191c9-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="191c9-121">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="191c9-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="191c9-122">Ottiene un puntatore a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per questo oggetto `ICorDebugNativeFrame` .</span><span class="sxs-lookup"><span data-stu-id="191c9-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="191c9-123">Metodo SetIP</span><span class="sxs-lookup"><span data-stu-id="191c9-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="191c9-124">Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="191c9-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="191c9-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="191c9-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="191c9-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="191c9-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="191c9-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="191c9-127">Requirements</span></span>  
 <span data-ttu-id="191c9-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="191c9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="191c9-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="191c9-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="191c9-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="191c9-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="191c9-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="191c9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191c9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191c9-132">See also</span></span>

- [<span data-ttu-id="191c9-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="191c9-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
