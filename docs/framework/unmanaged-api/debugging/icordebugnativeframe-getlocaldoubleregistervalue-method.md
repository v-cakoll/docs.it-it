---
title: Metodo ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 21c4d00e4156b9db27ae4188aace19764a2be53e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213075"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="5f5ab-102">Metodo ICorDebugNativeFrame::GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="5f5ab-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="5f5ab-103">Ottiene il valore di un argomento o di una variabile locale archiviata nei due registri specificati per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f5ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f5ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f5ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f5ab-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="5f5ab-106">in Valore dell'enumerazione "CorDebugRegister" che specifica il registro contenente la parola alta del valore.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="5f5ab-107">in Valore dell' `CorDebugRegister` enumerazione che specifica il registro contenente la parola bassa del valore.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5f5ab-108">in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il `pvSigBlob` parametro.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5f5ab-109">in `PCCOR_SIGNATURE`Valore che punta alla firma dei metadati binaria del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5f5ab-110">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nei registri specificati.</span><span class="sxs-lookup"><span data-stu-id="5f5ab-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f5ab-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f5ab-111">Remarks</span></span>  
 <span data-ttu-id="5f5ab-112">Il `GetLocalDoubleRegisterValue` metodo può essere usato in un frame nativo o in un frame compilato con JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="5f5ab-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f5ab-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f5ab-113">Requirements</span></span>  
 <span data-ttu-id="5f5ab-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f5ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f5ab-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f5ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f5ab-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f5ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f5ab-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f5ab-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f5ab-118">See also</span></span>
