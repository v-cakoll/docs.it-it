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
ms.openlocfilehash: 22722e4d602bdb9df9877b2199b4d4271a4d3105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792726"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="58729-102">Metodo ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="58729-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="58729-103">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="58729-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58729-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58729-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58729-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58729-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="58729-106">out Valore booleano che specifica se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="58729-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58729-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58729-107">Return Value</span></span>  
 <span data-ttu-id="58729-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="58729-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="58729-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58729-109">HRESULT</span></span>|<span data-ttu-id="58729-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58729-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58729-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="58729-111">S_OK</span></span>|<span data-ttu-id="58729-112">Stato figlio restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="58729-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="58729-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58729-113">E_FAIL</span></span>|<span data-ttu-id="58729-114">Non è stato possibile restituire lo stato figlio.</span><span class="sxs-lookup"><span data-stu-id="58729-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="58729-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="58729-115">E_INVALIDARG</span></span>|<span data-ttu-id="58729-116">`pIsChild` è null.</span><span class="sxs-lookup"><span data-stu-id="58729-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="58729-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="58729-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58729-118">Note</span><span class="sxs-lookup"><span data-stu-id="58729-118">Remarks</span></span>  
 <span data-ttu-id="58729-119">Il metodo `IsChild` restituisce `true` se l'oggetto frame su cui si chiama il metodo è un elemento figlio di un altro frame.</span><span class="sxs-lookup"><span data-stu-id="58729-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="58729-120">In tal caso, utilizzare il metodo [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) per verificare se un frame è il relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="58729-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58729-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="58729-121">Requirements</span></span>  
 <span data-ttu-id="58729-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58729-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58729-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58729-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58729-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58729-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58729-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58729-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58729-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58729-126">See also</span></span>

- [<span data-ttu-id="58729-127">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="58729-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="58729-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="58729-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="58729-129">Debug</span><span class="sxs-lookup"><span data-stu-id="58729-129">Debugging</span></span>](index.md)
