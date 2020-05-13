---
title: Metodo ICorDebugNativeFrame2::GetStackParameterSize
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: b88b3907eb555050de93f35411629b2bd30c7375
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212945"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="4a4a3-102">Metodo ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="4a4a3-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="4a4a3-103">Restituisce la dimensione cumulativa dei parametri nello stack nei sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a4a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a4a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a4a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a4a3-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="4a4a3-106">out Puntatore alla dimensione cumulativa dei parametri nello stack.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a4a3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a4a3-107">Return Value</span></span>  
 <span data-ttu-id="4a4a3-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4a4a3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a4a3-109">HRESULT</span></span>|<span data-ttu-id="4a4a3-110">Description</span><span class="sxs-lookup"><span data-stu-id="4a4a3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a4a3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a4a3-111">S_OK</span></span>|<span data-ttu-id="4a4a3-112">La dimensione dello stack è stata restituita correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="4a4a3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4a4a3-113">S_FALSE</span></span>|<span data-ttu-id="4a4a3-114">`GetStackParameterSize`è stato chiamato su una piattaforma non x86.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="4a4a3-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a4a3-115">E_FAIL</span></span>|<span data-ttu-id="4a4a3-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="4a4a3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4a4a3-117">E_INVALIDARG</span></span>|<span data-ttu-id="4a4a3-118">`pSize`È `null` .</span><span class="sxs-lookup"><span data-stu-id="4a4a3-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4a4a3-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4a4a3-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a4a3-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4a4a3-120">Remarks</span></span>  
 <span data-ttu-id="4a4a3-121">I metodi [ICorDebugStackWalk](icordebugstackwalk-interface.md) non regolano il puntatore dello stack per i parametri che vengono inseriti nello stack.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="4a4a3-122">In alternativa, è possibile usare il valore restituito da `GetStackParameterSize` per regolare il puntatore dello stack per il seeding di un oggetto di rimozione nativo, che si adatta ai parametri.</span><span class="sxs-lookup"><span data-stu-id="4a4a3-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a4a3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a4a3-123">Requirements</span></span>  
 <span data-ttu-id="4a4a3-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a4a3-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a4a3-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a4a3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a4a3-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a4a3-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a4a3-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a4a3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4a3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a4a3-128">See also</span></span>

- [<span data-ttu-id="4a4a3-129">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="4a4a3-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="4a4a3-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a4a3-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4a4a3-131">Debug</span><span class="sxs-lookup"><span data-stu-id="4a4a3-131">Debugging</span></span>](index.md)
