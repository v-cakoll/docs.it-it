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
ms.openlocfilehash: 539fa612234c4cc37bed5a8fd4b1e727a35b1d6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096396"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="0c0d5-102">Metodo ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="0c0d5-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="0c0d5-103">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c0d5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c0d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c0d5-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="0c0d5-106">out Valore booleano che specifica se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c0d5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c0d5-107">Return Value</span></span>  
 <span data-ttu-id="0c0d5-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0c0d5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c0d5-109">HRESULT</span></span>|<span data-ttu-id="0c0d5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c0d5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c0d5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c0d5-111">S_OK</span></span>|<span data-ttu-id="0c0d5-112">Stato figlio restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="0c0d5-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c0d5-113">E_FAIL</span></span>|<span data-ttu-id="0c0d5-114">Non è stato possibile restituire lo stato figlio.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="0c0d5-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c0d5-115">E_INVALIDARG</span></span>|<span data-ttu-id="0c0d5-116">`pIsChild` è null.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0c0d5-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="0c0d5-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c0d5-118">Note</span><span class="sxs-lookup"><span data-stu-id="0c0d5-118">Remarks</span></span>  
 <span data-ttu-id="0c0d5-119">Il metodo `IsChild` restituisce `true` se l'oggetto frame su cui si chiama il metodo è un elemento figlio di un altro frame.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="0c0d5-120">In tal caso, utilizzare il metodo [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) per verificare se un frame è il relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0c0d5-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c0d5-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c0d5-121">Requirements</span></span>  
 <span data-ttu-id="0c0d5-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c0d5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0d5-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c0d5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c0d5-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c0d5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c0d5-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c0d5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0d5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c0d5-126">See also</span></span>

- [<span data-ttu-id="0c0d5-127">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="0c0d5-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="0c0d5-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0c0d5-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0c0d5-129">Debug</span><span class="sxs-lookup"><span data-stu-id="0c0d5-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
