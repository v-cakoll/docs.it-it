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
ms.openlocfilehash: d44d7c23f88f5ea93f608d06b69f69b2c3637b5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096838"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="05799-102">Metodo ICorDebugNativeFrame::GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="05799-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="05799-103">Ottiene il valore di un argomento o di una variabile locale, di cui la parola bassa e la parola alta vengono archiviati nella posizione di memoria e nel registro specificato rispettivamente per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="05799-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05799-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05799-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05799-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05799-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="05799-106">in Valore dell'enumerazione "CorDebugRegister" che specifica il registro contenente la parola alta del valore.</span><span class="sxs-lookup"><span data-stu-id="05799-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="05799-107">in Valore `CORDB_ADDRESS` che specifica la posizione di memoria contenente la parola bassa del valore.</span><span class="sxs-lookup"><span data-stu-id="05799-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="05799-108">in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il parametro `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="05799-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="05799-109">in Valore `PCCOR_SIGNATURE` che punta alla firma dei metadati binaria del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="05799-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="05799-110">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel registro e nella posizione di memoria specificati.</span><span class="sxs-lookup"><span data-stu-id="05799-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05799-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05799-111">Requirements</span></span>  
 <span data-ttu-id="05799-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05799-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05799-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05799-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05799-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05799-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05799-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05799-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05799-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05799-116">See also</span></span>
