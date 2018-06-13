---
title: Metodo ICorDebugNativeFrame::GetLocalMemoryRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44f220f12f72ca8d0be6a9fc50b363c9bccb85fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417589"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="ee1b5-102">Metodo ICorDebugNativeFrame::GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="ee1b5-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="ee1b5-103">Ottiene il valore di un argomento o una variabile locale, di cui la parola meno significativa e word alto sono archiviati registro specificato e la posizione di memoria, rispettivamente, per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="ee1b5-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee1b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee1b5-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee1b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee1b5-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="ee1b5-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica la posizione di memoria che contiene la parola elevata del valore.</span><span class="sxs-lookup"><span data-stu-id="ee1b5-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="ee1b5-107">[in] Valore dell'enumerazione che specifica il registro contenente la Word meno significativa del valore "CorDebugRegister".</span><span class="sxs-lookup"><span data-stu-id="ee1b5-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ee1b5-108">[in] Valore intero che specifica la dimensione della firma binaria dei metadati a cui fa riferimento il `pvSigBlob` parametro.</span><span class="sxs-lookup"><span data-stu-id="ee1b5-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ee1b5-109">[in] Oggetto `PCCOR_SIGNATURE` che punta alla firma binaria dei metadati del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="ee1b5-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ee1b5-110">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel percorso di registro e di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="ee1b5-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee1b5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee1b5-111">Requirements</span></span>  
 <span data-ttu-id="ee1b5-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee1b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1b5-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ee1b5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee1b5-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ee1b5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee1b5-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1b5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee1b5-116">See Also</span></span>  
 
