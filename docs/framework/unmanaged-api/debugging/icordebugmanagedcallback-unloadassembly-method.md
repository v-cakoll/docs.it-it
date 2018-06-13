---
title: Metodo ICorDebugManagedCallback::UnloadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a892012e872dcf44512adbe0d6890812d84ed899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412594"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="bce36-102">Metodo ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="bce36-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="bce36-103">Notifica al debugger che un assembly di common language runtime è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="bce36-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bce36-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bce36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bce36-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bce36-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="bce36-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="bce36-107">[in] Un puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="bce36-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bce36-108">Note</span><span class="sxs-lookup"><span data-stu-id="bce36-108">Remarks</span></span>  
 <span data-ttu-id="bce36-109">L'assembly non deve essere utilizzato dopo questo callback.</span><span class="sxs-lookup"><span data-stu-id="bce36-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bce36-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bce36-110">Requirements</span></span>  
 <span data-ttu-id="bce36-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce36-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bce36-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bce36-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bce36-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bce36-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce36-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce36-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bce36-115">See Also</span></span>  
 [<span data-ttu-id="bce36-116">Metodo LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="bce36-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="bce36-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="bce36-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
