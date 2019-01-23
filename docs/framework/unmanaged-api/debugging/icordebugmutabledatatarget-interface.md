---
title: Interfaccia ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f63343b43481d1d91d1db30cd2ace3214c5590a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492299"
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="b14b0-102">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="b14b0-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="b14b0-103">Estende la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="b14b0-103">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b14b0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b14b0-104">Methods</span></span>  
  
|<span data-ttu-id="b14b0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b14b0-105">Method</span></span>|<span data-ttu-id="b14b0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b14b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b14b0-107">Metodo ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="b14b0-107">ContinueStatusChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="b14b0-108">Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="b14b0-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="b14b0-109">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="b14b0-109">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="b14b0-110">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="b14b0-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="b14b0-111">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="b14b0-111">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="b14b0-112">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b14b0-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b14b0-113">Note</span><span class="sxs-lookup"><span data-stu-id="b14b0-113">Remarks</span></span>  
 <span data-ttu-id="b14b0-114">Questa estensione per il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia può essere implementata dagli strumenti che vuole modificare il processo di destinazione (ad esempio, per eseguire debug attivo invasivo) di debug.</span><span class="sxs-lookup"><span data-stu-id="b14b0-114">This extension to the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="b14b0-115">Tutti questi metodi sono facoltativi. Se infatti non si implementa questa interfaccia o si verifica un errore durante le chiamate a questi metodi, non si perde alcuna funzionalità principale di debug basata su ispezione.</span><span class="sxs-lookup"><span data-stu-id="b14b0-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="b14b0-116">Qualsiasi `HRESULT` di errore di questi metodi verrà propagato all'esterno come `HRESULT` della chiamata al metodo ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="b14b0-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="b14b0-117">Si noti che una sola chiamata al metodo ICorDebug può restituire più modifiche e non esistono meccanismi che assicurano che le modifiche correlate vengano applicate in modo transazionale (tutte o nessuna).</span><span class="sxs-lookup"><span data-stu-id="b14b0-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="b14b0-118">Se quindi una modifica non riesce dopo che altre (per la stessa chiamata a ICorDebug) hanno avuto esito positivo, il processo di destinazione potrà rimanere in uno stato incoerente e il debug potrà diventare inaffidabile.</span><span class="sxs-lookup"><span data-stu-id="b14b0-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14b0-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b14b0-119">Requirements</span></span>  
 <span data-ttu-id="b14b0-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b14b0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14b0-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b14b0-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b14b0-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b14b0-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b14b0-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14b0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14b0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b14b0-124">See also</span></span>
- [<span data-ttu-id="b14b0-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b14b0-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b14b0-126">Debug</span><span class="sxs-lookup"><span data-stu-id="b14b0-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
