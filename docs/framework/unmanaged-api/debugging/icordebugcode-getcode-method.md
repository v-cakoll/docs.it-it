---
title: Metodo ICorDebugCode::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178991"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="05478-102">Metodo ICorDebugCode::GetCode</span><span class="sxs-lookup"><span data-stu-id="05478-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="05478-103">Ottiene tutto il codice per la funzione specificata, formattato per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="05478-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="05478-104">Questo metodo è stato deprecato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="05478-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="05478-105">Utilizzare [invece ICorDebugCode2::GetCodeChunks.](icordebugcode2-getcodechunks-method.md)</span><span class="sxs-lookup"><span data-stu-id="05478-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05478-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05478-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05478-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="05478-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="05478-108">[in] Offset dell'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="05478-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="05478-109">[in] Offset della fine della funzione.</span><span class="sxs-lookup"><span data-stu-id="05478-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="05478-110">[in] Dimensione della `buffer` matrice in cui verrà restituito il codice.</span><span class="sxs-lookup"><span data-stu-id="05478-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="05478-111">[fuori] Matrice in cui verrà restituito il codice.</span><span class="sxs-lookup"><span data-stu-id="05478-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="05478-112">[fuori] Numero di byte restituiti.</span><span class="sxs-lookup"><span data-stu-id="05478-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05478-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="05478-113">Remarks</span></span>  
 <span data-ttu-id="05478-114">Se il codice della funzione è stato suddiviso in più blocchi, vengono concatenati in ordine di offset nativo crescente.</span><span class="sxs-lookup"><span data-stu-id="05478-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="05478-115">I limiti delle istruzioni non vengono controllati.</span><span class="sxs-lookup"><span data-stu-id="05478-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05478-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05478-116">Requirements</span></span>  
 <span data-ttu-id="05478-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05478-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05478-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05478-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05478-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05478-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05478-120">Versioni di **.NET Framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="05478-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05478-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05478-121">See also</span></span>

- [<span data-ttu-id="05478-122">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="05478-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
