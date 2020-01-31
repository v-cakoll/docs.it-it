---
title: Interfaccia ICorDebugDataTarget
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: 9029d53872108bc1953fd22c584b6e01a6f3c7ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788860"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="c9c7d-102">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="c9c7d-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="c9c7d-103">Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9c7d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c9c7d-104">Methods</span></span>  
  
|<span data-ttu-id="c9c7d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c9c7d-105">Method</span></span>|<span data-ttu-id="c9c7d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9c7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9c7d-107">Metodo GetPlatform</span><span class="sxs-lookup"><span data-stu-id="c9c7d-107">GetPlatform Method</span></span>](icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="c9c7d-108">Fornisce informazioni sulla piattaforma, tra cui l'architettura del processore e il sistema operativo in cui è in esecuzione il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="c9c7d-109">Metodo ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="c9c7d-109">ReadVirtual Method</span></span>](icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="c9c7d-110">Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="c9c7d-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c9c7d-111">GetThreadContext Method</span></span>](icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="c9c7d-112">Richiede il contesto del thread corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9c7d-113">Note</span><span class="sxs-lookup"><span data-stu-id="c9c7d-113">Remarks</span></span>  
 <span data-ttu-id="c9c7d-114">`ICorDebugDataTarget` e i relativi metodi hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9c7d-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="c9c7d-115">I servizi di debug chiamano metodi su questa interfaccia per accedere alla memoria e ad altri dati nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="c9c7d-116">Il client del debugger deve implementare questa interfaccia in modo appropriato per la destinazione specifica (ad esempio, un processo attivo o un dump della memoria).</span><span class="sxs-lookup"><span data-stu-id="c9c7d-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="c9c7d-117">I metodi di `ICorDebugDataTarget` possono essere richiamati solo dall'interno dei metodi implementati in altre interfacce `ICorDebug*`.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="c9c7d-118">In questo modo si garantisce che il client del debugger disponga del controllo su quale thread viene richiamato e quando.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="c9c7d-119">L'implementazione `ICorDebugDataTarget` deve sempre restituire informazioni aggiornate sulla destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="c9c7d-120">Il processo di destinazione deve essere arrestato e non modificato in alcun modo durante la chiamata di `ICorDebug*` interfacce (e di conseguenza `ICorDebugDataTarget` metodi).</span><span class="sxs-lookup"><span data-stu-id="c9c7d-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="c9c7d-121">Se la destinazione è un processo attivo e il relativo stato viene modificato, è necessario chiamare nuovamente il metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) per fornire un'istanza di ICorDebugProcess sostitutiva.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9c7d-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c9c7d-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c7d-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c9c7d-123">Requirements</span></span>  
 <span data-ttu-id="c9c7d-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9c7d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c7d-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9c7d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9c7d-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9c7d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9c7d-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c7d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c7d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9c7d-128">See also</span></span>

- [<span data-ttu-id="c9c7d-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c9c7d-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c9c7d-130">Debug</span><span class="sxs-lookup"><span data-stu-id="c9c7d-130">Debugging</span></span>](index.md)
