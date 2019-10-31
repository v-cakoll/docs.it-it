---
title: Interfaccia ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 1ea0274adc12f3a99df0422bfc0b5180f0ef5596
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131384"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="f1ace-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f1ace-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="f1ace-103">Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="f1ace-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1ace-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f1ace-104">Methods</span></span>  
  
|<span data-ttu-id="f1ace-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f1ace-105">Method</span></span>|<span data-ttu-id="f1ace-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1ace-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1ace-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="f1ace-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="f1ace-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="f1ace-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="f1ace-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="f1ace-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="f1ace-110">Ottiene una maschera di bit che indica i registri in questo `ICorDebugRegisterSet` sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="f1ace-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="f1ace-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f1ace-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="f1ace-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f1ace-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="f1ace-113">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="f1ace-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="f1ace-114">Non implementato per la versione di .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1ace-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="f1ace-115">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f1ace-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="f1ace-116">Non implementato per la .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1ace-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ace-117">Note</span><span class="sxs-lookup"><span data-stu-id="f1ace-117">Remarks</span></span>  
 <span data-ttu-id="f1ace-118">L'interfaccia `ICorDebugRegisterSet` supporta solo registri a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="f1ace-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="f1ace-119">Usare l'interfaccia [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f1ace-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1ace-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f1ace-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ace-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1ace-121">Requirements</span></span>  
 <span data-ttu-id="f1ace-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ace-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ace-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1ace-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1ace-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ace-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ace-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ace-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ace-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ace-126">See also</span></span>

- [<span data-ttu-id="f1ace-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f1ace-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f1ace-128">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f1ace-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
