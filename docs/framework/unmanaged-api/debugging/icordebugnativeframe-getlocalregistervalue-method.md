---
title: Metodo ICorDebugNativeFrame::GetLocalRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
ms.openlocfilehash: 132e0868426670ba61d8ee12ba7007be1a8a52de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139403"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="84def-102">Metodo ICorDebugNativeFrame::GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="84def-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="84def-103">Ottiene il valore di un argomento o di una variabile locale archiviata nel registro specificato per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="84def-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84def-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84def-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84def-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84def-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="84def-106">in Valore dell'enumerazione "CorDebugRegister" che specifica il registro che contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="84def-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="84def-107">in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il parametro `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="84def-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="84def-108">in Valore `PCCOR_SIGNATURE` che punta alla firma dei metadati binaria del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="84def-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="84def-109">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel registro specificato.</span><span class="sxs-lookup"><span data-stu-id="84def-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84def-110">Note</span><span class="sxs-lookup"><span data-stu-id="84def-110">Remarks</span></span>  
 <span data-ttu-id="84def-111">Il metodo `GetLocalRegisterValue` può essere usato in un frame nativo o in un frame compilato con JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="84def-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84def-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84def-112">Requirements</span></span>  
 <span data-ttu-id="84def-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84def-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84def-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84def-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84def-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84def-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84def-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84def-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84def-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84def-117">See also</span></span>
