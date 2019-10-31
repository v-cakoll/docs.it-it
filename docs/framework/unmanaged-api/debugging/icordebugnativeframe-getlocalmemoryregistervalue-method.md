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
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137277"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="e41e5-102">Metodo ICorDebugNativeFrame::GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="e41e5-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="e41e5-103">Ottiene il valore di un argomento o di una variabile locale, di cui la parola bassa e la parola alta vengono archiviate rispettivamente nel registro e nella posizione di memoria specificati per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="e41e5-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e41e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e41e5-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="e41e5-106">in Valore `CORDB_ADDRESS` che specifica la posizione di memoria contenente la parola alta del valore.</span><span class="sxs-lookup"><span data-stu-id="e41e5-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="e41e5-107">in Valore dell'enumerazione "CorDebugRegister" che specifica il registro contenente la parola bassa del valore.</span><span class="sxs-lookup"><span data-stu-id="e41e5-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e41e5-108">in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il parametro `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e41e5-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e41e5-109">in Valore `PCCOR_SIGNATURE` che punta alla firma dei metadati binaria del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="e41e5-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e41e5-110">out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel registro e nella posizione di memoria specificati.</span><span class="sxs-lookup"><span data-stu-id="e41e5-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41e5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e41e5-111">Requirements</span></span>  
 <span data-ttu-id="e41e5-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e41e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e41e5-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e41e5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e41e5-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e41e5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e41e5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e41e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41e5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e41e5-116">See also</span></span>
