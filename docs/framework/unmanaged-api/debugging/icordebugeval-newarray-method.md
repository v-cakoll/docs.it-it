---
title: Metodo ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 13ac5379992f4e768b09a03d31591143ba9bf627
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788716"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="037c5-102">Metodo ICorDebugEval::NewArray</span><span class="sxs-lookup"><span data-stu-id="037c5-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="037c5-103">Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="037c5-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="037c5-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="037c5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="037c5-105">Usare invece [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .</span><span class="sxs-lookup"><span data-stu-id="037c5-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="037c5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="037c5-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="037c5-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="037c5-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="037c5-108">in Valore dell'enumerazione CorElementType che specifica il tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="037c5-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="037c5-109">in Puntatore a un oggetto ICorDebugClass che specifica la classe dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="037c5-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="037c5-110">Questo valore può essere null se il tipo di elemento è un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="037c5-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="037c5-111">in Numero di dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="037c5-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="037c5-112">Nel .NET Framework 2,0, questo valore deve essere 1.</span><span class="sxs-lookup"><span data-stu-id="037c5-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="037c5-113">in Dimensione, in byte, di ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="037c5-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="037c5-114">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="037c5-114">[in] Optional.</span></span> <span data-ttu-id="037c5-115">Limite inferiore di ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="037c5-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="037c5-116">Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="037c5-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="037c5-117">Note</span><span class="sxs-lookup"><span data-stu-id="037c5-117">Remarks</span></span>  
 <span data-ttu-id="037c5-118">La matrice viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="037c5-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="037c5-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="037c5-119">Requirements</span></span>  
 <span data-ttu-id="037c5-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="037c5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="037c5-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="037c5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="037c5-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="037c5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="037c5-123">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="037c5-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
