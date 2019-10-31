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
ms.openlocfilehash: 5826297d8151cf05e1ec08acbf5c9cd381d2452b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137796"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="86323-102">Metodo ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="86323-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="86323-103">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="86323-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86323-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86323-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86323-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86323-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="86323-106">out Puntatore a un intero che rappresenta il numero di versione della funzione rappresentata da questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="86323-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86323-107">Note</span><span class="sxs-lookup"><span data-stu-id="86323-107">Remarks</span></span>  
 <span data-ttu-id="86323-108">Il runtime tiene traccia del numero di modifiche che si sono verificate per ogni modulo durante una sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="86323-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="86323-109">Il numero di versione di una funzione è uno più del numero della modifica che ha introdotto la funzione.</span><span class="sxs-lookup"><span data-stu-id="86323-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="86323-110">La versione originale della funzione è la versione 1.</span><span class="sxs-lookup"><span data-stu-id="86323-110">The function's original version is version 1.</span></span> <span data-ttu-id="86323-111">Il numero viene incrementato per un modulo ogni volta che viene chiamato [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) sul modulo.</span><span class="sxs-lookup"><span data-stu-id="86323-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="86323-112">Pertanto, se il corpo di una funzione è stato sostituito nella prima e terza chiamata a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` possibile restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3.</span><span class="sxs-lookup"><span data-stu-id="86323-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="86323-113">Questa funzione non avrebbe la versione 3.</span><span class="sxs-lookup"><span data-stu-id="86323-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="86323-114">Il numero di versione viene rilevato separatamente per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="86323-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="86323-115">Quindi, se si eseguono quattro modifiche sul modulo 1 e nessuna sul modulo 2, la modifica successiva nel modulo 1 assegnerà un numero di versione di 6 a tutte le funzioni modificate nel modulo 1.</span><span class="sxs-lookup"><span data-stu-id="86323-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="86323-116">Se la stessa modifica tocca il modulo 2, le funzioni nel modulo 2 otterranno il numero di versione 2.</span><span class="sxs-lookup"><span data-stu-id="86323-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="86323-117">Il numero di versione ottenuto dal metodo `GetVersionNumber` può essere inferiore a quello ottenuto da [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="86323-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="86323-118">Il metodo [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) esegue la stessa operazione di `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="86323-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86323-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86323-119">Requirements</span></span>  
 <span data-ttu-id="86323-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86323-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86323-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86323-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86323-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86323-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86323-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86323-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
