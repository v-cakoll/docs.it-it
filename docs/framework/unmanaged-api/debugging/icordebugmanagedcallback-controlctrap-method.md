---
title: Metodo ICorDebugManagedCallback::ControlCTrap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ControlCTrap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c5de52b810efeaf7b5c103dcd39a37a37ab3272
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="79b28-102">Metodo ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="79b28-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="79b28-103">Notifica al debugger che CTRL + C viene intercettato nel processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="79b28-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79b28-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79b28-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79b28-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="79b28-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui viene intercettato CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="79b28-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79b28-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="79b28-107">Return Value</span></span>  
  
|<span data-ttu-id="79b28-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79b28-108">HRESULT</span></span>|<span data-ttu-id="79b28-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79b28-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79b28-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="79b28-110">S_OK</span></span>|<span data-ttu-id="79b28-111">Il debugger gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="79b28-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="79b28-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="79b28-112">S_FALSE</span></span>|<span data-ttu-id="79b28-113">Il debugger non gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="79b28-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79b28-114">Note</span><span class="sxs-lookup"><span data-stu-id="79b28-114">Remarks</span></span>  
 <span data-ttu-id="79b28-115">Per questo callback, vengono arrestati tutti i domini applicazione all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="79b28-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b28-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79b28-116">Requirements</span></span>  
 <span data-ttu-id="79b28-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b28-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b28-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="79b28-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79b28-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79b28-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79b28-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79b28-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b28-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b28-121">See Also</span></span>  
 [<span data-ttu-id="79b28-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="79b28-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
