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
ms.openlocfilehash: b98077914d680c908587649fdd517aca9c8dcd40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125434"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="42827-102">Metodo ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="42827-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="42827-103">Scollega il debugger dal dominio del processo o dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="42827-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42827-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42827-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="42827-105">Note</span><span class="sxs-lookup"><span data-stu-id="42827-105">Remarks</span></span>  
 <span data-ttu-id="42827-106">Il processo o il dominio applicazione continua l'esecuzione normalmente, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e non si verificheranno ulteriori callback.</span><span class="sxs-lookup"><span data-stu-id="42827-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="42827-107">Nel .NET Framework versione 2,0, se è abilitato il debug non gestito, questo metodo avrà esito negativo a causa delle limitazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="42827-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42827-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42827-108">Requirements</span></span>  
 <span data-ttu-id="42827-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42827-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42827-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42827-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42827-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42827-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42827-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42827-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42827-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42827-113">See also</span></span>
