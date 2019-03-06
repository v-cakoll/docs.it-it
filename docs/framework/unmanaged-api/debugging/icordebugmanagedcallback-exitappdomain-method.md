---
title: Metodo ICorDebugManagedCallback::ExitAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1b6d23ab5d773f6f25becefd45895c365271e6a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476191"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="0050b-102">Metodo ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="0050b-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="0050b-103">Notifica al debugger che è stato chiuso un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0050b-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0050b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0050b-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0050b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0050b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0050b-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene il dominio applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="0050b-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0050b-107">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="0050b-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0050b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0050b-108">Requirements</span></span>  
 <span data-ttu-id="0050b-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0050b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0050b-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0050b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0050b-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0050b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0050b-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0050b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0050b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0050b-113">See also</span></span>
- [<span data-ttu-id="0050b-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0050b-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
