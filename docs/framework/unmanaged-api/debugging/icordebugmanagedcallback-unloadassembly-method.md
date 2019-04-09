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
ms.openlocfilehash: 6e770602858761dbcf15c233dceebfd35be106aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214131"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="3a9df-102">Metodo ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="3a9df-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="3a9df-103">Notifica al debugger che è stato scaricato un assembly di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3a9df-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a9df-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a9df-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3a9df-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3a9df-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="3a9df-107">[in] Un puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3a9df-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a9df-108">Note</span><span class="sxs-lookup"><span data-stu-id="3a9df-108">Remarks</span></span>  
 <span data-ttu-id="3a9df-109">L'assembly non deve essere utilizzato dopo questo callback.</span><span class="sxs-lookup"><span data-stu-id="3a9df-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9df-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a9df-110">Requirements</span></span>  
 <span data-ttu-id="3a9df-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a9df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9df-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a9df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a9df-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a9df-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3a9df-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3a9df-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a9df-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a9df-115">See also</span></span>

- [<span data-ttu-id="3a9df-116">Metodo LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="3a9df-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="3a9df-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3a9df-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
