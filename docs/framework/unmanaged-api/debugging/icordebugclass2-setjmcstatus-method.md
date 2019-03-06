---
title: Metodo ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471381"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="91aa2-102">Metodo ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="91aa2-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="91aa2-103">Per ogni metodo della classe, imposta un valore che indica se il metodo è codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91aa2-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91aa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91aa2-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91aa2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="91aa2-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="91aa2-106">[in] Impostare su `true` per indicare che il metodo è definito dall'utente codice; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="91aa2-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91aa2-107">Note</span><span class="sxs-lookup"><span data-stu-id="91aa2-107">Remarks</span></span>  
 <span data-ttu-id="91aa2-108">Un just my code (JMC) ignorerà il codice non definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91aa2-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="91aa2-109">Codice definito dall'utente deve essere un subset di debug.</span><span class="sxs-lookup"><span data-stu-id="91aa2-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="91aa2-110">`SetJMCStatus` Restituisce un valore HRESULT di S_FALSE se non riesce a impostare il valore per qualsiasi metodo, anche se è stata imposta il valore per tutti gli altri metodi.</span><span class="sxs-lookup"><span data-stu-id="91aa2-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91aa2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91aa2-111">Requirements</span></span>  
 <span data-ttu-id="91aa2-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91aa2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91aa2-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91aa2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91aa2-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91aa2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91aa2-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91aa2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
