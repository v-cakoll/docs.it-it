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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6419a525a8a542295751defb97e67a83220730b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965072"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="65a88-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="65a88-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="65a88-103">Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="65a88-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65a88-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="65a88-104">Methods</span></span>  
  
|<span data-ttu-id="65a88-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="65a88-105">Method</span></span>|<span data-ttu-id="65a88-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="65a88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65a88-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="65a88-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="65a88-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="65a88-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="65a88-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="65a88-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="65a88-110">Ottiene una maschera di bit che indica `ICorDebugRegisterSet` i registri attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="65a88-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="65a88-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="65a88-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="65a88-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="65a88-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="65a88-113">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="65a88-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="65a88-114">Non implementato per la versione di .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="65a88-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="65a88-115">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="65a88-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="65a88-116">Non implementato per la .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="65a88-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65a88-117">Note</span><span class="sxs-lookup"><span data-stu-id="65a88-117">Remarks</span></span>  
 <span data-ttu-id="65a88-118">L' `ICorDebugRegisterSet` interfaccia supporta solo registri a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="65a88-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="65a88-119">Usare l'interfaccia [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="65a88-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65a88-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="65a88-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a88-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65a88-121">Requirements</span></span>  
 <span data-ttu-id="65a88-122">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a88-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a88-123">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="65a88-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65a88-124">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a88-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a88-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a88-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a88-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65a88-126">See also</span></span>

- [<span data-ttu-id="65a88-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="65a88-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="65a88-128">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="65a88-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
