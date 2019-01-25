---
title: Metodo ICorDebugNativeFrame::GetLocalMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e8d0c16000c78fab0371b68c3a350bd2018aa1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664525"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="0c5ec-102">Metodo ICorDebugNativeFrame::GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="0c5ec-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="0c5ec-103">Ottiene il valore di un argomento o una variabile locale viene archiviato nella posizione di memoria specificata per il frame nativo.</span><span class="sxs-lookup"><span data-stu-id="0c5ec-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c5ec-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c5ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c5ec-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="0c5ec-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica la posizione di memoria che contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="0c5ec-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0c5ec-107">[in] Intero che specifica le dimensioni della firma binaria dei metadati che fa riferimento il `pvSigBlob` parametro.</span><span class="sxs-lookup"><span data-stu-id="0c5ec-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="0c5ec-108">[in] Oggetto `PCCOR_SIGNATURE` valore che punta alla firma binaria dei metadati del tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="0c5ec-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0c5ec-109">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nella posizione di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="0c5ec-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5ec-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c5ec-110">Requirements</span></span>  
 <span data-ttu-id="0c5ec-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c5ec-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5ec-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c5ec-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c5ec-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c5ec-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c5ec-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5ec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5ec-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5ec-115">See also</span></span>

