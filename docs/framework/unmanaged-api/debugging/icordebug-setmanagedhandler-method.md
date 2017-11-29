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
ms.openlocfilehash: 06f0989058ed21e736fde0aee5f1cd1dd66e0ca8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="5cc55-102">Metodo ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="5cc55-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="5cc55-103">Specifica l'oggetto di gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="5cc55-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cc55-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cc55-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cc55-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="5cc55-106">[in] Un puntatore a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) oggetto, ovvero l'oggetto gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="5cc55-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cc55-107">Note</span><span class="sxs-lookup"><span data-stu-id="5cc55-107">Remarks</span></span>  
 <span data-ttu-id="5cc55-108">`SetManagedHandler`deve essere chiamato in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="5cc55-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="5cc55-109">Se il `ICorDebugManagedCallback` implementazione non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione che viene eseguito il debug, `SetManagedHandler` restituisce un HRESULT di tipo E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="5cc55-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc55-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cc55-110">Requirements</span></span>  
 <span data-ttu-id="5cc55-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc55-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc55-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5cc55-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cc55-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cc55-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cc55-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc55-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc55-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cc55-115">See Also</span></span>  
 [<span data-ttu-id="5cc55-116">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5cc55-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
