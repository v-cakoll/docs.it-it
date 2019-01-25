---
title: Metodo ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f2dae147f8667a73036dbcf873e2082996b2755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666985"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="f279e-102">Metodo ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="f279e-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="f279e-103">Scollega debugger dal dominio dell'applicazione o processo.</span><span class="sxs-lookup"><span data-stu-id="f279e-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f279e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f279e-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f279e-105">Note</span><span class="sxs-lookup"><span data-stu-id="f279e-105">Remarks</span></span>  
 <span data-ttu-id="f279e-106">Il processo o dominio applicazione continua l'esecuzione in genere, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e si verificherà alcun callback ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="f279e-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="f279e-107">In .NET Framework versione 2.0, se il debug non gestito è abilitato, questo metodo avrà esito negativo a causa di limitazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f279e-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f279e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f279e-108">Requirements</span></span>  
 <span data-ttu-id="f279e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f279e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f279e-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f279e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f279e-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f279e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f279e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f279e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f279e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f279e-113">See also</span></span>

