---
title: Metodo ICorDebugManagedCallback::NameChange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.NameChange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31539413597c65b553794f07b1eeecdf3943f908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="63d5e-102">Metodo ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="63d5e-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="63d5e-103">Notifica al debugger che il nome del dominio applicazione o un thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="63d5e-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63d5e-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63d5e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63d5e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="63d5e-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che è stato una modifica del nome oppure che contiene il thread che ha una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="63d5e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="63d5e-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che ha una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="63d5e-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d5e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63d5e-108">Requirements</span></span>  
 <span data-ttu-id="63d5e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d5e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d5e-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="63d5e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63d5e-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d5e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d5e-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d5e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d5e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d5e-113">See Also</span></span>  
 [<span data-ttu-id="63d5e-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="63d5e-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
