---
title: Metodo ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178457"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="46195-102">Metodo ICorDebugThread3::GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="46195-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="46195-103">Restituisce una matrice di frame interni ([iCorDebugInternalFrame2](icordebuginternalframe2-interface.md) oggetti) nello stack.</span><span class="sxs-lookup"><span data-stu-id="46195-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46195-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46195-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="46195-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46195-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="46195-106">[in] Il numero di fotogrammi interni previsti in `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="46195-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="46195-107">[fuori] Puntatore a `ULONG32` un che contiene il numero di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="46195-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="46195-108">[in, out] Puntatore all'indirizzo di una matrice di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="46195-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46195-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="46195-109">Return Value</span></span>  
 <span data-ttu-id="46195-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="46195-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="46195-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46195-111">HRESULT</span></span>|<span data-ttu-id="46195-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46195-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46195-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="46195-113">S_OK</span></span>|<span data-ttu-id="46195-114">L'oggetto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) è stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="46195-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="46195-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="46195-115">E_INVALIDARG</span></span>|<span data-ttu-id="46195-116">`cInternalFrames`non è `ppInternalFrames` zero `null`e `pcInternalFrames` `null`è , o è .</span><span class="sxs-lookup"><span data-stu-id="46195-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="46195-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="46195-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="46195-118">`ppInternalFrames`è inferiore al conteggio dei fotogrammi interni.</span><span class="sxs-lookup"><span data-stu-id="46195-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="46195-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="46195-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46195-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="46195-120">Remarks</span></span>  
 <span data-ttu-id="46195-121">I frame interni sono strutture di dati inserite nello stack dal runtime per archiviare i dati temporanei.</span><span class="sxs-lookup"><span data-stu-id="46195-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="46195-122">Quando si `GetActiveInternalFrames`chiama per la `cInternalFrames` prima volta , è `ppInternalFrames` necessario impostare il parametro su 0 (zero) e il parametro su null.</span><span class="sxs-lookup"><span data-stu-id="46195-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="46195-123">Quando `GetActiveInternalFrames` termina `pcInternalFrames` per la prima volta, contiene il conteggio dei frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="46195-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="46195-124">`GetActiveInternalFrames`dovrebbe quindi essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="46195-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="46195-125">È necessario passare il`pcInternalFrames`conteggio `cInternalFrames` corretto ( ) nel parametro e `ppInternalFrames`specificare un puntatore a una matrice di dimensioni appropriate in .</span><span class="sxs-lookup"><span data-stu-id="46195-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="46195-126">Utilizzare il [iCorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) metodo per restituire gli stack frame effettivi.</span><span class="sxs-lookup"><span data-stu-id="46195-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46195-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46195-127">Requirements</span></span>  
 <span data-ttu-id="46195-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46195-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46195-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46195-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46195-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46195-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46195-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46195-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46195-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46195-132">See also</span></span>

- [<span data-ttu-id="46195-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="46195-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="46195-134">Debug</span><span class="sxs-lookup"><span data-stu-id="46195-134">Debugging</span></span>](index.md)
