---
title: Metodo ICorDebugManagedCallback::UnloadClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e034f6950cc9d77ef4db350475379aa5c497f7f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="1c862-102">Metodo ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="1c862-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="1c862-103">Notifica al debugger che è in corso lo scaricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="1c862-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c862-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c862-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c862-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c862-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1c862-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente la classe.</span><span class="sxs-lookup"><span data-stu-id="1c862-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="1c862-107">[in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="1c862-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c862-108">Note</span><span class="sxs-lookup"><span data-stu-id="1c862-108">Remarks</span></span>  
 <span data-ttu-id="1c862-109">La classe non può farvi riferimento dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c862-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c862-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c862-110">Requirements</span></span>  
 <span data-ttu-id="1c862-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c862-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c862-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1c862-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c862-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c862-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c862-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c862-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c862-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c862-115">See Also</span></span>  
 [<span data-ttu-id="1c862-116">LoadClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="1c862-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)  
 [<span data-ttu-id="1c862-117">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1c862-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
