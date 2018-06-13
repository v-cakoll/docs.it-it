---
title: Metodo ICorDebugNativeFrame::GetLocalRegisterMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5605f7b2ad9ba42a340906559838de22ac79f789
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416680"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="2832f-102">Metodo ICorDebugNativeFrame::GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="2832f-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="2832f-103">Ottiene il valore di un argomento o una variabile locale, in cui word basso e word alto vengono archiviati nella posizione di memoria e nel registro viene specificato, rispettivamente, per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="2832f-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2832f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2832f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2832f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2832f-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="2832f-106">[in] Valore dell'enumerazione che specifica il registro contenente la parola elevata del valore "CorDebugRegister".</span><span class="sxs-lookup"><span data-stu-id="2832f-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="2832f-107">[in] Oggetto `CORDB_ADDRESS` valore che specifica la posizione di memoria che contiene il word basso del valore.</span><span class="sxs-lookup"><span data-stu-id="2832f-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2832f-108">[in] Valore intero che specifica la dimensione della firma binaria dei metadati a cui fa riferimento il `pvSigBlob` parametro.</span><span class="sxs-lookup"><span data-stu-id="2832f-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2832f-109">[in] Oggetto `PCCOR_SIGNATURE` che punta alla firma binaria dei metadati del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="2832f-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2832f-110">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel percorso di registro e di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="2832f-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2832f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2832f-111">Requirements</span></span>  
 <span data-ttu-id="2832f-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2832f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2832f-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2832f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2832f-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2832f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2832f-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2832f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2832f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2832f-116">See Also</span></span>  
 
