---
title: Metodo ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcf97f9fffabb9ae9579016517cfc335e6f783a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404573"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="78a15-102">Metodo ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="78a15-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="78a15-103">Specifica l'oggetto di gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="78a15-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78a15-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78a15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78a15-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="78a15-106">[in] Un puntatore a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) oggetto, ovvero l'oggetto gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="78a15-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78a15-107">Note</span><span class="sxs-lookup"><span data-stu-id="78a15-107">Remarks</span></span>  
 <span data-ttu-id="78a15-108">`SetManagedHandler` deve essere chiamato in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="78a15-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="78a15-109">Se il `ICorDebugManagedCallback` implementazione non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione che viene eseguito il debug, `SetManagedHandler` restituisce un HRESULT di tipo E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="78a15-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a15-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78a15-110">Requirements</span></span>  
 <span data-ttu-id="78a15-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a15-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="78a15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78a15-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="78a15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78a15-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a15-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a15-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78a15-115">See Also</span></span>  
 [<span data-ttu-id="78a15-116">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="78a15-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
