---
title: Metodo ICorDebugManagedCallback::ExitProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff80462c722a84ef68ac8c6703ded3e7138a1939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="6d035-102">Metodo ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="6d035-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="6d035-103">Notifica al debugger che un processo è terminato.</span><span class="sxs-lookup"><span data-stu-id="6d035-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d035-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d035-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d035-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d035-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6d035-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="6d035-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d035-107">Note</span><span class="sxs-lookup"><span data-stu-id="6d035-107">Remarks</span></span>  
 <span data-ttu-id="6d035-108">È possibile proseguire da un `ExitProcess` evento.</span><span class="sxs-lookup"><span data-stu-id="6d035-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="6d035-109">Questo evento potrebbe essere generato in modo asincrono e gli altri eventi mentre il processo da arrestare.</span><span class="sxs-lookup"><span data-stu-id="6d035-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="6d035-110">Ciò può verificarsi se il processo viene interrotto mentre arrestato, in genere a causa di alcune forza esterna.</span><span class="sxs-lookup"><span data-stu-id="6d035-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="6d035-111">Se common language runtime (CLR) sta già inviando un callback gestito, questo evento verrà ritardato fino a dopo che ha restituito il callback.</span><span class="sxs-lookup"><span data-stu-id="6d035-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="6d035-112">Il `ExitProcess` evento è l'unico evento di uscita o scaricamento che viene chiamato in fase di arresto.</span><span class="sxs-lookup"><span data-stu-id="6d035-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d035-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d035-113">Requirements</span></span>  
 <span data-ttu-id="6d035-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d035-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d035-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6d035-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d035-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d035-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d035-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d035-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d035-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d035-118">See Also</span></span>  
 [<span data-ttu-id="6d035-119">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d035-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
