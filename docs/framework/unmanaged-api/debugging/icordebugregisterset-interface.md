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
ms.openlocfilehash: f435db28d5c85d576f69e7612841fc46ae142332
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792075"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="9fdf6-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="9fdf6-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="9fdf6-103">Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9fdf6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9fdf6-104">Methods</span></span>  
  
|<span data-ttu-id="9fdf6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9fdf6-105">Method</span></span>|<span data-ttu-id="9fdf6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fdf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9fdf6-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="9fdf6-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="9fdf6-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="9fdf6-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="9fdf6-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="9fdf6-110">Ottiene una maschera di bit che indica i registri in questo `ICorDebugRegisterSet` sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="9fdf6-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="9fdf6-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="9fdf6-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="9fdf6-113">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="9fdf6-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="9fdf6-114">Non implementato per la versione di .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="9fdf6-115">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="9fdf6-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="9fdf6-116">Non implementato per la .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fdf6-117">Note</span><span class="sxs-lookup"><span data-stu-id="9fdf6-117">Remarks</span></span>  
 <span data-ttu-id="9fdf6-118">L'interfaccia `ICorDebugRegisterSet` supporta solo registri a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="9fdf6-119">Usare l'interfaccia [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fdf6-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9fdf6-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fdf6-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9fdf6-121">Requirements</span></span>  
 <span data-ttu-id="9fdf6-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fdf6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fdf6-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fdf6-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fdf6-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fdf6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fdf6-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fdf6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdf6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fdf6-126">See also</span></span>

- [<span data-ttu-id="9fdf6-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9fdf6-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9fdf6-128">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="9fdf6-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
