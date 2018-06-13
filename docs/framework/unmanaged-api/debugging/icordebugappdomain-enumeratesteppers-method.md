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
ms.openlocfilehash: 7bf3aa6d883dffece6ba89d41005499cc6206906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401291"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="4b8b4-102">Metodo ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="4b8b4-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="4b8b4-103">Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b8b4-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b8b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b8b4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b8b4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b8b4-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="4b8b4-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugStepperEnum che è l'enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b8b4-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8b4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b8b4-107">Requirements</span></span>  
 <span data-ttu-id="4b8b4-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b8b4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b8b4-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4b8b4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b8b4-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4b8b4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b8b4-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b8b4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
