---
title: Metodo ICorDebugManagedCallback::NameChange
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8bc4eb1895fe67c25354b42fe3ae1ffe80bca58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491321"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="4db0f-102">Metodo ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="4db0f-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="4db0f-103">Notifica al debugger che il nome di un dominio dell'applicazione o un thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="4db0f-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4db0f-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4db0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4db0f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4db0f-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che è stato modificato un nome oppure che contiene il thread che aveva una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="4db0f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4db0f-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che aveva una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="4db0f-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db0f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4db0f-108">Requirements</span></span>  
 <span data-ttu-id="4db0f-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4db0f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db0f-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4db0f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4db0f-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4db0f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4db0f-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db0f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db0f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4db0f-113">See also</span></span>
- [<span data-ttu-id="4db0f-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4db0f-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
