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
ms.openlocfilehash: 59a497d203d241bbc6e0f884007d4a401c112073
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893657"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="dbb0a-102">Metodo ICorDebugCode::GetCode</span><span class="sxs-lookup"><span data-stu-id="dbb0a-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="dbb0a-103">Ottiene tutto il codice per la funzione specificata, formattato per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="dbb0a-104">Questo metodo è stato deprecato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="dbb0a-105">Usare invece [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dbb0a-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb0a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbb0a-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dbb0a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="dbb0a-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="dbb0a-108">in Offset dell'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="dbb0a-109">in Offset della fine della funzione.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="dbb0a-110">in Dimensione della `buffer` matrice in cui verrà restituito il codice.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="dbb0a-111">out Matrice nella quale verrà restituito il codice.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="dbb0a-112">out Numero di byte restituiti.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbb0a-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dbb0a-113">Remarks</span></span>  
 <span data-ttu-id="dbb0a-114">Se il codice della funzione è stato diviso in più blocchi, viene concatenato in ordine di aumento dell'offset nativo.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="dbb0a-115">I limiti delle istruzioni non sono controllati.</span><span class="sxs-lookup"><span data-stu-id="dbb0a-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb0a-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dbb0a-116">Requirements</span></span>  
 <span data-ttu-id="dbb0a-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbb0a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb0a-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbb0a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbb0a-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb0a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb0a-120">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="dbb0a-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb0a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbb0a-121">See also</span></span>

- [<span data-ttu-id="dbb0a-122">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="dbb0a-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
