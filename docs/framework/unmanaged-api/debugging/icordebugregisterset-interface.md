---
title: Interfaccia ICorDebugRegisterSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet
helpviewer_keywords: ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ccff205758dee2ffc6a6432ab20b3310147eb06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="cb090-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="cb090-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="cb090-103">Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="cb090-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb090-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb090-104">Methods</span></span>  
  
|<span data-ttu-id="cb090-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb090-105">Method</span></span>|<span data-ttu-id="cb090-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb090-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb090-107">GetRegisters (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb090-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="cb090-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="cb090-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="cb090-109">GetRegistersAvailable (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb090-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="cb090-110">Ottiene una maschera di bit che indica quali registri in `ICorDebugRegisterSet` sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="cb090-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="cb090-111">GetThreadContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb090-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="cb090-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="cb090-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="cb090-113">SetRegisters (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb090-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="cb090-114">Non implementato per .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="cb090-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="cb090-115">SetThreadContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb090-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="cb090-116">Non implementato per .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="cb090-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb090-117">Note</span><span class="sxs-lookup"><span data-stu-id="cb090-117">Remarks</span></span>  
 <span data-ttu-id="cb090-118">Il `ICorDebugRegisterSet` interfaccia supporta registri solo 32 bit.</span><span class="sxs-lookup"><span data-stu-id="cb090-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="cb090-119">Utilizzare il [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaccia sulle piattaforme, ad esempio IA-64 che richiedono registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cb090-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb090-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="cb090-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb090-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb090-121">Requirements</span></span>  
 <span data-ttu-id="cb090-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb090-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb090-123">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cb090-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb090-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb090-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb090-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb090-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb090-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb090-126">See Also</span></span>  
 [<span data-ttu-id="cb090-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cb090-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cb090-128">ICorDebugRegisterSet2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="cb090-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
