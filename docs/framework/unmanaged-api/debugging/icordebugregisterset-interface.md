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
ms.openlocfilehash: 7c60fa775b82372b50d1eb3891f107b97df3e73a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378262"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="9b5aa-102">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="9b5aa-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="9b5aa-103">Rappresenta il set di registri disponibili nel computer in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b5aa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9b5aa-104">Methods</span></span>  
  
|<span data-ttu-id="9b5aa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9b5aa-105">Method</span></span>|<span data-ttu-id="9b5aa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b5aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b5aa-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="9b5aa-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="9b5aa-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="9b5aa-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="9b5aa-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="9b5aa-110">Ottiene una maschera di bit che indica i registri `ICorDebugRegisterSet` attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="9b5aa-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="9b5aa-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="9b5aa-112">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="9b5aa-113">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="9b5aa-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="9b5aa-114">Non implementato per la versione di .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="9b5aa-115">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="9b5aa-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="9b5aa-116">Non implementato per la .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b5aa-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b5aa-117">Remarks</span></span>  
 <span data-ttu-id="9b5aa-118">L' `ICorDebugRegisterSet` interfaccia supporta solo registri a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="9b5aa-119">Usare l'interfaccia [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) sulle piattaforme, ad esempio IA-64, che richiedono registri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b5aa-120">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9b5aa-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b5aa-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b5aa-121">Requirements</span></span>  
 <span data-ttu-id="9b5aa-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b5aa-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b5aa-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b5aa-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b5aa-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b5aa-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b5aa-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b5aa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5aa-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b5aa-126">See also</span></span>

- [<span data-ttu-id="9b5aa-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9b5aa-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9b5aa-128">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="9b5aa-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
