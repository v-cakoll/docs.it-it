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
ms.openlocfilehash: 953b7c1cb5e471072776fe03e53a46d3ff19c0ac
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379861"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="2ac6c-102">Metodo ICorDebugThread3::GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="2ac6c-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="2ac6c-103">Restituisce una matrice di frame interni (oggetti[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) nello stack.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ac6c-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ac6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ac6c-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="2ac6c-106">in Numero di frame interni previsti in `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="2ac6c-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="2ac6c-107">out Puntatore a un oggetto `ULONG32` che contiene il numero di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="2ac6c-108">[in, out] Puntatore all'indirizzo di una matrice di frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ac6c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2ac6c-109">Return Value</span></span>  
 <span data-ttu-id="2ac6c-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2ac6c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ac6c-111">HRESULT</span></span>|<span data-ttu-id="2ac6c-112">Description</span><span class="sxs-lookup"><span data-stu-id="2ac6c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ac6c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ac6c-113">S_OK</span></span>|<span data-ttu-id="2ac6c-114">Creazione dell'oggetto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) completata.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="2ac6c-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2ac6c-115">E_INVALIDARG</span></span>|<span data-ttu-id="2ac6c-116">`cInternalFrames`non è zero e `ppInternalFrames` è `null` oppure `pcInternalFrames` è `null` .</span><span class="sxs-lookup"><span data-stu-id="2ac6c-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="2ac6c-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="2ac6c-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="2ac6c-118">`ppInternalFrames`è inferiore al numero di frame interni.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2ac6c-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="2ac6c-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ac6c-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2ac6c-120">Remarks</span></span>  
 <span data-ttu-id="2ac6c-121">I frame interni sono strutture di dati inserite nello stack dal runtime per archiviare i dati temporanei.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="2ac6c-122">Quando si chiama prima `GetActiveInternalFrames` , è necessario impostare il `cInternalFrames` parametro su 0 (zero) e il `ppInternalFrames` parametro su null.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="2ac6c-123">Quando viene restituito per la `GetActiveInternalFrames` prima volta, `pcInternalFrames` contiene il conteggio dei frame interni nello stack.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="2ac6c-124">`GetActiveInternalFrames`deve quindi essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="2ac6c-125">È necessario passare il conteggio appropriato ( `pcInternalFrames` ) nel `cInternalFrames` parametro e specificare un puntatore a una matrice di dimensioni appropriate in `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="2ac6c-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="2ac6c-126">Usare il metodo [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) per restituire gli stack frame effettivi.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac6c-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ac6c-127">Requirements</span></span>  
 <span data-ttu-id="2ac6c-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac6c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac6c-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ac6c-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ac6c-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac6c-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac6c-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac6c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac6c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ac6c-132">See also</span></span>

- [<span data-ttu-id="2ac6c-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2ac6c-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2ac6c-134">Debug</span><span class="sxs-lookup"><span data-stu-id="2ac6c-134">Debugging</span></span>](index.md)
