---
title: Metodo ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377162"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="5f50f-102">Metodo ICorDebugThread2::GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="5f50f-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="5f50f-103">Ottiene informazioni sulla funzione attiva in ogni frame del thread.</span><span class="sxs-lookup"><span data-stu-id="5f50f-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f50f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f50f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f50f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f50f-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="5f50f-106">[in] Dimensione della matrice `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="5f50f-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="5f50f-107">out Puntatore al numero di oggetti restituiti nella `pFunctions` matrice.</span><span class="sxs-lookup"><span data-stu-id="5f50f-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="5f50f-108">Il numero di oggetti restituiti sarà uguale al numero di frame gestiti nello stack.</span><span class="sxs-lookup"><span data-stu-id="5f50f-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="5f50f-109">[in, out] Matrice di oggetti COR_ACTIVE_FUNCTION, ognuno dei quali contiene informazioni sulle funzioni attive nei frame del thread.</span><span class="sxs-lookup"><span data-stu-id="5f50f-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="5f50f-110">Il primo elemento verrà usato per il frame foglia e così via tornando alla radice dello stack.</span><span class="sxs-lookup"><span data-stu-id="5f50f-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f50f-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f50f-111">Remarks</span></span>  
 <span data-ttu-id="5f50f-112">Se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce solo il numero di funzioni presenti nello stack.</span><span class="sxs-lookup"><span data-stu-id="5f50f-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="5f50f-113">Ovvero, se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce un valore solo in `pcFunctions` .</span><span class="sxs-lookup"><span data-stu-id="5f50f-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="5f50f-114">Il `GetActiveFunctions` metodo è concepito come ottimizzazione per ottenere le stesse informazioni dai frame in una traccia dello stack e include solo i frame per i quali sarebbe stato disponibile un oggetto ICorDebugILFrame nell'analisi dello stack completa.</span><span class="sxs-lookup"><span data-stu-id="5f50f-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f50f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f50f-115">Requirements</span></span>  
 <span data-ttu-id="5f50f-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f50f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f50f-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f50f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f50f-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f50f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f50f-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f50f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
