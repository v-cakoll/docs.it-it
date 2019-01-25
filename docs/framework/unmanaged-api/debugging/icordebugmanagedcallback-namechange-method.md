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
ms.openlocfilehash: c33f287cf7ccadeb75ba0bbccf9118aeedc1f942
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607432"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="b4744-102">Metodo ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="b4744-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="b4744-103">Notifica al debugger che il nome di un dominio dell'applicazione o un thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="b4744-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4744-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4744-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4744-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4744-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b4744-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che è stato modificato un nome oppure che contiene il thread che aveva una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="b4744-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b4744-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread che aveva una modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="b4744-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4744-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4744-108">Requirements</span></span>  
 <span data-ttu-id="b4744-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4744-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4744-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4744-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4744-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4744-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4744-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4744-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4744-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4744-113">See also</span></span>
- [<span data-ttu-id="b4744-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b4744-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
