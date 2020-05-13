---
title: Interfaccia ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: fcf7521f8261c8f8f84c7a9a9deb4b7a7d739c6e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210007"
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="0aa14-102">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="0aa14-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="0aa14-103">Estende l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per supportare destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="0aa14-103">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0aa14-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0aa14-104">Methods</span></span>  
  
|<span data-ttu-id="0aa14-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0aa14-105">Method</span></span>|<span data-ttu-id="0aa14-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0aa14-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0aa14-107">Metodo ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="0aa14-107">ContinueStatusChanged Method</span></span>](icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="0aa14-108">Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0aa14-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="0aa14-109">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0aa14-109">SetThreadContext Method</span></span>](icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="0aa14-110">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="0aa14-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="0aa14-111">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="0aa14-111">WriteVirtual Method</span></span>](icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="0aa14-112">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0aa14-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aa14-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0aa14-113">Remarks</span></span>  
 <span data-ttu-id="0aa14-114">Questa estensione per l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) può essere implementata da strumenti di debug che vogliono modificare il processo di destinazione (ad esempio, per eseguire il debug invasivo Live).</span><span class="sxs-lookup"><span data-stu-id="0aa14-114">This extension to the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="0aa14-115">Tutti questi metodi sono facoltativi. Se infatti non si implementa questa interfaccia o si verifica un errore durante le chiamate a questi metodi, non si perde alcuna funzionalità principale di debug basata su ispezione.</span><span class="sxs-lookup"><span data-stu-id="0aa14-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="0aa14-116">Qualsiasi `HRESULT` di errore di questi metodi verrà propagato all'esterno come `HRESULT` della chiamata al metodo ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="0aa14-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="0aa14-117">Si noti che una sola chiamata al metodo ICorDebug può restituire più modifiche e non esistono meccanismi che assicurano che le modifiche correlate vengano applicate in modo transazionale (tutte o nessuna).</span><span class="sxs-lookup"><span data-stu-id="0aa14-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="0aa14-118">Se quindi una modifica non riesce dopo che altre (per la stessa chiamata a ICorDebug) hanno avuto esito positivo, il processo di destinazione potrà rimanere in uno stato incoerente e il debug potrà diventare inaffidabile.</span><span class="sxs-lookup"><span data-stu-id="0aa14-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa14-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0aa14-119">Requirements</span></span>  
 <span data-ttu-id="0aa14-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aa14-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa14-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0aa14-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0aa14-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aa14-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aa14-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa14-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa14-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa14-124">See also</span></span>

- [<span data-ttu-id="0aa14-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0aa14-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0aa14-126">Debug</span><span class="sxs-lookup"><span data-stu-id="0aa14-126">Debugging</span></span>](index.md)
