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
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135239"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="c0c08-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c0c08-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="c0c08-103">Rappresenta il set di registri disponibili sul computer che esegue codice.</span><span class="sxs-lookup"><span data-stu-id="c0c08-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0c08-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0c08-104">Methods</span></span>  
  
|<span data-ttu-id="c0c08-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c0c08-105">Method</span></span>|<span data-ttu-id="c0c08-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0c08-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0c08-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="c0c08-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="c0c08-108">Ottiene il valore di ogni registro (nel computer che esegue codice) che viene specificato per la maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="c0c08-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="c0c08-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="c0c08-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="c0c08-110">Ottiene una maschera di bit che indica quali registri in `ICorDebugRegisterSet` sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="c0c08-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="c0c08-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c0c08-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="c0c08-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="c0c08-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="c0c08-113">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="c0c08-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="c0c08-114">Non implementato per .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="c0c08-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="c0c08-115">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c0c08-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="c0c08-116">Non implementato per .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c0c08-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c08-117">Note</span><span class="sxs-lookup"><span data-stu-id="c0c08-117">Remarks</span></span>  
 <span data-ttu-id="c0c08-118">Il `ICorDebugRegisterSet` interfaccia supporta registri solo 32 bit.</span><span class="sxs-lookup"><span data-stu-id="c0c08-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="c0c08-119">Usare la [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaccia su piattaforme, ad esempio IA-64 che richiedono i registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c0c08-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0c08-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c0c08-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0c08-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0c08-121">Requirements</span></span>  
 <span data-ttu-id="c0c08-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0c08-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c08-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0c08-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0c08-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0c08-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0c08-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c08-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c08-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0c08-126">See also</span></span>

- [<span data-ttu-id="c0c08-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c0c08-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c0c08-128">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="c0c08-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
