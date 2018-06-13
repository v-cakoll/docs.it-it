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
ms.openlocfilehash: f909eddde182a73709be9ca5cafec6285db46b4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412854"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="a45b9-102">Metodo ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="a45b9-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="a45b9-103">Notifica al debugger che un dominio applicazione è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="a45b9-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a45b9-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a45b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a45b9-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a45b9-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene il dominio applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="a45b9-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a45b9-107">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="a45b9-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a45b9-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a45b9-108">Requirements</span></span>  
 <span data-ttu-id="a45b9-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a45b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a45b9-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a45b9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a45b9-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a45b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a45b9-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a45b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45b9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a45b9-113">See Also</span></span>  
 [<span data-ttu-id="a45b9-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a45b9-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
