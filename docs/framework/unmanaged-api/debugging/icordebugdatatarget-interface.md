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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930828"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="3dbab-102">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="3dbab-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="3dbab-103">Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3dbab-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dbab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3dbab-104">Methods</span></span>  
  
|<span data-ttu-id="3dbab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3dbab-105">Method</span></span>|<span data-ttu-id="3dbab-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="3dbab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dbab-107">Metodo GetPlatform</span><span class="sxs-lookup"><span data-stu-id="3dbab-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="3dbab-108">Fornisce informazioni sulla piattaforma, tra cui l'architettura del processore e il sistema operativo in cui è in esecuzione il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3dbab-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="3dbab-109">Metodo ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="3dbab-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="3dbab-110">Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.</span><span class="sxs-lookup"><span data-stu-id="3dbab-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="3dbab-111">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3dbab-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="3dbab-112">Richiede il contesto del thread corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="3dbab-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dbab-113">Note</span><span class="sxs-lookup"><span data-stu-id="3dbab-113">Remarks</span></span>  
 <span data-ttu-id="3dbab-114">`ICorDebugDataTarget`e i relativi metodi hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="3dbab-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="3dbab-115">I servizi di debug chiamano metodi su questa interfaccia per accedere alla memoria e ad altri dati nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3dbab-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="3dbab-116">Il client del debugger deve implementare questa interfaccia in modo appropriato per la destinazione specifica (ad esempio, un processo attivo o un dump della memoria).</span><span class="sxs-lookup"><span data-stu-id="3dbab-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="3dbab-117">I `ICorDebugDataTarget` metodi possono essere richiamati solo dall'interno dei metodi `ICorDebug*` implementati in altre interfacce.</span><span class="sxs-lookup"><span data-stu-id="3dbab-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="3dbab-118">In questo modo si garantisce che il client del debugger disponga del controllo su quale thread viene richiamato e quando.</span><span class="sxs-lookup"><span data-stu-id="3dbab-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="3dbab-119">L' `ICorDebugDataTarget` implementazione deve sempre restituire informazioni aggiornate sulla destinazione.</span><span class="sxs-lookup"><span data-stu-id="3dbab-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="3dbab-120">Il processo di destinazione deve essere interrotto e non modificato in alcun modo `ICorDebug*` durante la chiamata di `ICorDebugDataTarget` interfacce (e di conseguenza metodi).</span><span class="sxs-lookup"><span data-stu-id="3dbab-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="3dbab-121">Se la destinazione è un processo attivo e il relativo stato viene modificato, è necessario chiamare nuovamente il metodo [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) per fornire un'istanza di ICorDebugProcess sostitutiva.</span><span class="sxs-lookup"><span data-stu-id="3dbab-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dbab-122">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="3dbab-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dbab-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3dbab-123">Requirements</span></span>  
 <span data-ttu-id="3dbab-124">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dbab-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dbab-125">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3dbab-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dbab-126">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dbab-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dbab-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dbab-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbab-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dbab-128">See also</span></span>

- [<span data-ttu-id="3dbab-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3dbab-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3dbab-130">Debug</span><span class="sxs-lookup"><span data-stu-id="3dbab-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
