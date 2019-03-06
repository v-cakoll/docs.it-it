---
title: Metodo ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e49c20d7627f666efd6561cee19ca505f723b714
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474436"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="84720-102">Metodo ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="84720-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="84720-103">Notifica al debugger che un modulo di common language runtime (CLR) è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="84720-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84720-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84720-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84720-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84720-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="84720-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="84720-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="84720-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="84720-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84720-108">Note</span><span class="sxs-lookup"><span data-stu-id="84720-108">Remarks</span></span>  
 <span data-ttu-id="84720-109">Il `LoadModule` callback fornisce un momento opportuno per esaminare i metadati per il modulo, impostare i flag del compilatore just-in-time (JIT) o abilitare o disabilitare i callback per il modulo di caricamento delle classi.</span><span class="sxs-lookup"><span data-stu-id="84720-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84720-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84720-110">Requirements</span></span>  
 <span data-ttu-id="84720-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84720-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84720-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84720-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84720-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84720-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84720-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84720-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84720-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84720-115">See also</span></span>
- [<span data-ttu-id="84720-116">Metodo UnloadModule</span><span class="sxs-lookup"><span data-stu-id="84720-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="84720-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="84720-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
