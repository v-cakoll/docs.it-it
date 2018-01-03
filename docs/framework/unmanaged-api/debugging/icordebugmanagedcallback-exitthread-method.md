---
title: Metodo ICorDebugManagedCallback::ExitThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c39a8c92a8c0be8d0607663a833ac7307ca26d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="f8f62-102">Metodo ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="f8f62-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="f8f62-103">Notifica al debugger che un thread che era in esecuzione il codice gestito è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="f8f62-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8f62-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8f62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8f62-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f8f62-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="f8f62-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="f8f62-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="f8f62-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8f62-108">Note</span><span class="sxs-lookup"><span data-stu-id="f8f62-108">Remarks</span></span>  
 <span data-ttu-id="f8f62-109">Una volta il `ExitThread` callback viene generato, il thread non verrà più visualizzato nelle enumerazioni dei thread.</span><span class="sxs-lookup"><span data-stu-id="f8f62-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f62-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8f62-110">Requirements</span></span>  
 <span data-ttu-id="f8f62-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8f62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f62-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f8f62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8f62-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8f62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8f62-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8f62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f62-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f62-115">See Also</span></span>  
 [<span data-ttu-id="f8f62-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f8f62-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
