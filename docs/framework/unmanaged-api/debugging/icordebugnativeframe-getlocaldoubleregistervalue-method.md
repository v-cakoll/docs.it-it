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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13e1e3369c4e7a185c2167facc8514b5cfc85a85
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115869"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="46dc9-102">Metodo ICorDebugNativeFrame::GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="46dc9-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="46dc9-103">Ottiene il valore di un argomento o una variabile locale che viene archiviato in due registri specificati per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="46dc9-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46dc9-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46dc9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46dc9-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="46dc9-106">[in] Valore dell'enumerazione che specifica il registro contenente la Word più significativa del valore "CorDebugRegister".</span><span class="sxs-lookup"><span data-stu-id="46dc9-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="46dc9-107">[in] Valore di `CorDebugRegister` enumerazione che specifica il registro contenente la Word meno significativa del valore.</span><span class="sxs-lookup"><span data-stu-id="46dc9-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="46dc9-108">[in] Intero che specifica le dimensioni della firma binaria dei metadati che fa riferimento il `pvSigBlob` parametro.</span><span class="sxs-lookup"><span data-stu-id="46dc9-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="46dc9-109">[in] Oggetto `PCCOR_SIGNATURE` valore che punta alla firma binaria dei metadati del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="46dc9-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="46dc9-110">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nei registri specificati.</span><span class="sxs-lookup"><span data-stu-id="46dc9-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46dc9-111">Note</span><span class="sxs-lookup"><span data-stu-id="46dc9-111">Remarks</span></span>  
 <span data-ttu-id="46dc9-112">Il `GetLocalDoubleRegisterValue` metodo può essere utilizzato in un frame nativo o un just-in-time (JIT)-frame compilato.</span><span class="sxs-lookup"><span data-stu-id="46dc9-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46dc9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46dc9-113">Requirements</span></span>  
 <span data-ttu-id="46dc9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46dc9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46dc9-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46dc9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46dc9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46dc9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46dc9-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46dc9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dc9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46dc9-118">See also</span></span>
