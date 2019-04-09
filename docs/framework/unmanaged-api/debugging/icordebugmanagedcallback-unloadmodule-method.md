---
title: Metodo ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12e42da015864e83663d2f4d74bab2a34052d760
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083544"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="e38bc-102">Metodo ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="e38bc-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="e38bc-103">Notifica al debugger che è stato scaricato un modulo di common language runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="e38bc-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e38bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e38bc-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e38bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e38bc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e38bc-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il modulo.</span><span class="sxs-lookup"><span data-stu-id="e38bc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="e38bc-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo.</span><span class="sxs-lookup"><span data-stu-id="e38bc-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e38bc-108">Note</span><span class="sxs-lookup"><span data-stu-id="e38bc-108">Remarks</span></span>  
 <span data-ttu-id="e38bc-109">Il modulo non deve essere utilizzato dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="e38bc-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e38bc-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e38bc-110">Requirements</span></span>  
 <span data-ttu-id="e38bc-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e38bc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e38bc-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e38bc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e38bc-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e38bc-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e38bc-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e38bc-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e38bc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e38bc-115">See also</span></span>

- [<span data-ttu-id="e38bc-116">Metodo LoadModule</span><span class="sxs-lookup"><span data-stu-id="e38bc-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="e38bc-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e38bc-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
