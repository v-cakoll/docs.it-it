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
ms.openlocfilehash: d85885d750f3c98e46b3e44418564da18850d3ec
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794492"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="f4cfb-102">Metodo ICorDebugFunction2::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="f4cfb-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="f4cfb-103">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4cfb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4cfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4cfb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4cfb-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="f4cfb-106">out Puntatore a un intero che rappresenta il numero di versione della funzione rappresentata da questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4cfb-107">Note</span><span class="sxs-lookup"><span data-stu-id="f4cfb-107">Remarks</span></span>  
 <span data-ttu-id="f4cfb-108">Il runtime tiene traccia del numero di modifiche che si sono verificate per ogni modulo durante una sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="f4cfb-109">Il numero di versione di una funzione è uno più del numero della modifica che ha introdotto la funzione.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="f4cfb-110">La versione originale della funzione è la versione 1.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-110">The function's original version is version 1.</span></span> <span data-ttu-id="f4cfb-111">Il numero viene incrementato per un modulo ogni volta che viene chiamato [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) sul modulo.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="f4cfb-112">Pertanto, se il corpo di una funzione è stato sostituito nella prima e terza chiamata a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` possibile restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="f4cfb-113">Questa funzione non avrebbe la versione 3.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="f4cfb-114">Il numero di versione viene rilevato separatamente per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="f4cfb-115">Quindi, se si eseguono quattro modifiche sul modulo 1 e nessuna sul modulo 2, la modifica successiva nel modulo 1 assegnerà un numero di versione di 6 a tutte le funzioni modificate nel modulo 1.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="f4cfb-116">Se la stessa modifica tocca il modulo 2, le funzioni nel modulo 2 otterranno il numero di versione 2.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="f4cfb-117">Il numero di versione ottenuto dal metodo `GetVersionNumber` può essere inferiore a quello ottenuto da [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4cfb-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="f4cfb-118">Il metodo [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) esegue la stessa operazione di `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="f4cfb-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4cfb-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f4cfb-119">Requirements</span></span>  
 <span data-ttu-id="f4cfb-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4cfb-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4cfb-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4cfb-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4cfb-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4cfb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4cfb-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4cfb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
