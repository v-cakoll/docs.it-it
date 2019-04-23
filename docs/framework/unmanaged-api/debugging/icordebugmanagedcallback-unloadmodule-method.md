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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083544"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="692ec-102">Metodo ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="692ec-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="692ec-103">Notifica al debugger che è stato scaricato un modulo di common language runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="692ec-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="692ec-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="692ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="692ec-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="692ec-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il modulo.</span><span class="sxs-lookup"><span data-stu-id="692ec-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="692ec-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo.</span><span class="sxs-lookup"><span data-stu-id="692ec-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="692ec-108">Note</span><span class="sxs-lookup"><span data-stu-id="692ec-108">Remarks</span></span>  
 <span data-ttu-id="692ec-109">Il modulo non deve essere utilizzato dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="692ec-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692ec-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="692ec-110">Requirements</span></span>  
 <span data-ttu-id="692ec-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="692ec-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692ec-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="692ec-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="692ec-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="692ec-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="692ec-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692ec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692ec-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="692ec-115">See also</span></span>

- [<span data-ttu-id="692ec-116">Metodo LoadModule</span><span class="sxs-lookup"><span data-stu-id="692ec-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="692ec-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="692ec-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
