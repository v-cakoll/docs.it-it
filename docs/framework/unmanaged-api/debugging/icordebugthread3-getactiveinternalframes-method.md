---
title: Metodo ICorDebugThread3::GetActiveInternalFrames
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b94827ac49c69c5e72c2e300a80914774cc498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="010e6-102">Metodo ICorDebugThread3::GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="010e6-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="010e6-103">Restituisce una matrice di frame interni ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetti) nello stack.</span><span class="sxs-lookup"><span data-stu-id="010e6-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="010e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="010e6-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="010e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="010e6-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="010e6-106">[in] Il numero di frame interni previsti in `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="010e6-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="010e6-107">[out] Un puntatore a un `ULONG32` che contiene il numero di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="010e6-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="010e6-108">[in, out] Un puntatore all'indirizzo di una matrice di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="010e6-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="010e6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="010e6-109">Return Value</span></span>  
 <span data-ttu-id="010e6-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="010e6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="010e6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="010e6-111">HRESULT</span></span>|<span data-ttu-id="010e6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="010e6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="010e6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="010e6-113">S_OK</span></span>|<span data-ttu-id="010e6-114">Il [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetto è stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="010e6-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="010e6-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="010e6-115">E_INVALIDARG</span></span>|<span data-ttu-id="010e6-116">`cInternalFrames`non è zero e `ppInternalFrames` è `null`, o `pcInternalFrames` è `null`.</span><span class="sxs-lookup"><span data-stu-id="010e6-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="010e6-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="010e6-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="010e6-118">`ppInternalFrames`è minore del numero di frame interni.</span><span class="sxs-lookup"><span data-stu-id="010e6-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="010e6-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="010e6-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="010e6-120">Note</span><span class="sxs-lookup"><span data-stu-id="010e6-120">Remarks</span></span>  
 <span data-ttu-id="010e6-121">Frame interni sono strutture di dati nello stack dal runtime per archiviare dati temporanei.</span><span class="sxs-lookup"><span data-stu-id="010e6-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="010e6-122">Quando si chiama innanzitutto `GetActiveInternalFrames`, è necessario impostare il `cInternalFrames` parametro su 0 (zero) e `ppInternalFrames` parametro su null.</span><span class="sxs-lookup"><span data-stu-id="010e6-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="010e6-123">Quando `GetActiveInternalFrames` restituita innanzitutto, `pcInternalFrames` contiene il numero di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="010e6-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="010e6-124">`GetActiveInternalFrames`deve quindi essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="010e6-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="010e6-125">È necessario passare il numero appropriato (`pcInternalFrames`) nei `cInternalFrames` parametro e specificare un puntatore a una matrice di dimensione appropriate in `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="010e6-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="010e6-126">Utilizzare il [GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) frame dello stack per restituire effettivo.</span><span class="sxs-lookup"><span data-stu-id="010e6-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="010e6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="010e6-127">Requirements</span></span>  
 <span data-ttu-id="010e6-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="010e6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="010e6-129">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="010e6-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="010e6-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="010e6-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="010e6-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="010e6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="010e6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="010e6-132">See Also</span></span>  
 [<span data-ttu-id="010e6-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="010e6-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="010e6-134">Debug</span><span class="sxs-lookup"><span data-stu-id="010e6-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
