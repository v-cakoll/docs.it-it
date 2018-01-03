---
title: Metodo ICorDebug::SetManagedHandler
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.SetManagedHandler
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dde32b6a8251474c4254e35a3a1ba3ba3bafcb8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="ca8f5-102">Metodo ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="ca8f5-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="ca8f5-103">Specifica l'oggetto di gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca8f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca8f5-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca8f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca8f5-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="ca8f5-106">[in] Un puntatore a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) oggetto, ovvero l'oggetto gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca8f5-107">Note</span><span class="sxs-lookup"><span data-stu-id="ca8f5-107">Remarks</span></span>  
 <span data-ttu-id="ca8f5-108">`SetManagedHandler`deve essere chiamato in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="ca8f5-109">Se il `ICorDebugManagedCallback` implementazione non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione che viene eseguito il debug, `SetManagedHandler` restituisce un HRESULT di tipo E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="ca8f5-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca8f5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca8f5-110">Requirements</span></span>  
 <span data-ttu-id="ca8f5-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca8f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca8f5-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ca8f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca8f5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca8f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca8f5-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca8f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8f5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca8f5-115">See Also</span></span>  
 [<span data-ttu-id="ca8f5-116">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ca8f5-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
