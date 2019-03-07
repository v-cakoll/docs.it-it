---
title: Metodo ICorDebugFunction2::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497171"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="aeebd-102">Metodo ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="aeebd-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="aeebd-103">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="aeebd-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeebd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aeebd-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aeebd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aeebd-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="aeebd-106">[out] Un puntatore a un integer che rappresenta il numero di versione della funzione rappresentata dall'oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="aeebd-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeebd-107">Note</span><span class="sxs-lookup"><span data-stu-id="aeebd-107">Remarks</span></span>  
 <span data-ttu-id="aeebd-108">Il runtime tiene traccia del numero di modifiche che sono state apportate a ogni modulo durante una sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="aeebd-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="aeebd-109">Il numero di versione di una funzione è una maggiore del numero della modifica che è stata introdotta la funzione.</span><span class="sxs-lookup"><span data-stu-id="aeebd-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="aeebd-110">La versione della funzione originale è la versione 1.</span><span class="sxs-lookup"><span data-stu-id="aeebd-110">The function's original version is version 1.</span></span> <span data-ttu-id="aeebd-111">Il numero viene incrementato ogni volta che per un modulo [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) viene chiamato su tale modulo.</span><span class="sxs-lookup"><span data-stu-id="aeebd-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="aeebd-112">Di conseguenza, se il corpo della funzione è stato sostituito nella chiamata al prima e il terza `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` potrebbe restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3.</span><span class="sxs-lookup"><span data-stu-id="aeebd-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="aeebd-113">(Tale funzione non potrebbe avere alcuna versione 3).</span><span class="sxs-lookup"><span data-stu-id="aeebd-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="aeebd-114">Il numero di versione viene registrato separatamente per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="aeebd-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="aeebd-115">Pertanto, se si eseguono quattro modifiche nel modulo 1 e nessuna nel modulo 2, la successiva modifica su 1 modulo assegnerà un numero di versione 6 per tutte le funzioni modificate nel modulo 1.</span><span class="sxs-lookup"><span data-stu-id="aeebd-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="aeebd-116">Se le stesse modifiche interessano modulo 2, le funzioni nel modulo 2 otterrà un numero di versione 2.</span><span class="sxs-lookup"><span data-stu-id="aeebd-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="aeebd-117">Il numero di versione ottenuto mediante la `GetVersionNumber` metodo potrebbe essere inferiore a quello ottenuto da [GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="aeebd-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="aeebd-118">Il [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo esegue la stessa operazione `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="aeebd-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aeebd-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aeebd-119">Requirements</span></span>  
 <span data-ttu-id="aeebd-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeebd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aeebd-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aeebd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aeebd-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aeebd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aeebd-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeebd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
