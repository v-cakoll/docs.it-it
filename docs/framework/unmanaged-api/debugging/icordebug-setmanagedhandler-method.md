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
ms.openlocfilehash: 54ef1cab27a39de39b39996729be6b8160570745
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788964"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="da32b-102">Metodo ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="da32b-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="da32b-103">Specifica l'oggetto gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="da32b-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da32b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da32b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da32b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da32b-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="da32b-106">in Puntatore a un oggetto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , che è l'oggetto del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="da32b-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da32b-107">Note</span><span class="sxs-lookup"><span data-stu-id="da32b-107">Remarks</span></span>  
 <span data-ttu-id="da32b-108">`SetManagedHandler` deve essere chiamato in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="da32b-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="da32b-109">Se l'implementazione del `ICorDebugManagedCallback` non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione di cui è in corso il debug, `SetManagedHandler` restituisce un valore HRESULT di E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="da32b-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da32b-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="da32b-110">Requirements</span></span>  
 <span data-ttu-id="da32b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da32b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da32b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da32b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da32b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da32b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da32b-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da32b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da32b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da32b-115">See also</span></span>

- [<span data-ttu-id="da32b-116">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="da32b-116">ICorDebug Interface</span></span>](icordebug-interface.md)
