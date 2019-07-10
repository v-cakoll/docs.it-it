---
title: Metodo ICorDebugAppDomain::EnumerateSteppers
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea2c72a91aaa09d1c2d0e0944b73beb9ea313d0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738034"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="2cfeb-102">Metodo ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="2cfeb-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="2cfeb-103">Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cfeb-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cfeb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cfeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cfeb-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="2cfeb-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugStepperEnum che è l'enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cfeb-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfeb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cfeb-107">Requirements</span></span>  
 <span data-ttu-id="2cfeb-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cfeb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cfeb-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cfeb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cfeb-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cfeb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cfeb-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cfeb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
