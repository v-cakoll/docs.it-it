---
title: Metodo ICorDebugManagedCallback::CreateProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bef3140717ff977fbfae813d0de89011b89ed062
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="8a837-102">Metodo ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="8a837-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="8a837-103">Notifica al debugger quando un processo è stato associato o avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="8a837-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a837-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a837-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a837-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a837-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="8a837-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che è stato associato o avviato.</span><span class="sxs-lookup"><span data-stu-id="8a837-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a837-107">Note</span><span class="sxs-lookup"><span data-stu-id="8a837-107">Remarks</span></span>  
 <span data-ttu-id="8a837-108">Questo metodo non viene chiamato finché non viene inizializzato common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8a837-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="8a837-109">La maggior parte del [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi restituirà CORDBG_E_NOTREADY prima il `CreateProcess` callback.</span><span class="sxs-lookup"><span data-stu-id="8a837-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a837-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a837-110">Requirements</span></span>  
 <span data-ttu-id="8a837-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a837-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a837-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8a837-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a837-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a837-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a837-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a837-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a837-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a837-115">See Also</span></span>  
 [<span data-ttu-id="8a837-116">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8a837-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
