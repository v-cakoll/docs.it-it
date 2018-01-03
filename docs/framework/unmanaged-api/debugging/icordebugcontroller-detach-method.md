---
title: Metodo ICorDebugController::Detach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Detach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59fe2c4bfbd91afd263a0ada1eb355aaa8914aa2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="7c059-102">Metodo ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="7c059-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="7c059-103">Disconnette il debugger dal dominio applicazione o processo.</span><span class="sxs-lookup"><span data-stu-id="7c059-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c059-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c059-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7c059-105">Note</span><span class="sxs-lookup"><span data-stu-id="7c059-105">Remarks</span></span>  
 <span data-ttu-id="7c059-106">Il processo o dominio applicazione continua l'esecuzione in genere, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e si verificherà alcun callback ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="7c059-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="7c059-107">In .NET Framework versione 2.0, se è abilitato il debug non gestito, questo metodo avrà esito negativo a causa di limitazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7c059-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c059-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c059-108">Requirements</span></span>  
 <span data-ttu-id="7c059-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c059-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c059-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7c059-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c059-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c059-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c059-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c059-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c059-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c059-113">See Also</span></span>  
 
