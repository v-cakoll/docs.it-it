---
title: Metodo ICorDebugNativeFrame2::IsChild
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550d25e995bdfe010fb1aa664a7c9882a775f4d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757167"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="65582-102">Metodo ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="65582-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="65582-103">Determina se il frame corrente è una cornice figlio.</span><span class="sxs-lookup"><span data-stu-id="65582-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65582-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65582-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65582-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65582-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="65582-106">[out] Valore booleano che specifica se il frame corrente è una cornice figlio.</span><span class="sxs-lookup"><span data-stu-id="65582-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65582-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65582-107">Return Value</span></span>  
 <span data-ttu-id="65582-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="65582-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65582-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65582-109">HRESULT</span></span>|<span data-ttu-id="65582-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65582-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65582-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="65582-111">S_OK</span></span>|<span data-ttu-id="65582-112">Lo stato figlio è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="65582-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="65582-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65582-113">E_FAIL</span></span>|<span data-ttu-id="65582-114">Lo stato del figlio non può essere restituito.</span><span class="sxs-lookup"><span data-stu-id="65582-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="65582-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="65582-115">E_INVALIDARG</span></span>|<span data-ttu-id="65582-116">`pIsChild` è null.</span><span class="sxs-lookup"><span data-stu-id="65582-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="65582-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="65582-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65582-118">Note</span><span class="sxs-lookup"><span data-stu-id="65582-118">Remarks</span></span>  
 <span data-ttu-id="65582-119">Il `IsChild` restituzione del metodo `true` se l'oggetto frame in cui si chiama il metodo è un elemento figlio di un altro frame.</span><span class="sxs-lookup"><span data-stu-id="65582-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="65582-120">In questo caso, usare il [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) metodo per verificare se un frame padre.</span><span class="sxs-lookup"><span data-stu-id="65582-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65582-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65582-121">Requirements</span></span>  
 <span data-ttu-id="65582-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65582-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65582-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65582-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65582-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65582-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65582-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65582-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65582-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65582-126">See also</span></span>

- [<span data-ttu-id="65582-127">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="65582-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="65582-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="65582-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="65582-129">Debug</span><span class="sxs-lookup"><span data-stu-id="65582-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
